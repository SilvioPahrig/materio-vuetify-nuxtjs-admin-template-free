<script lang="ts" setup>
import avatar1 from "@images/avatars/avatar-1.png";
import ProfileNavItems from '@/layouts/components/ProfilNavItems.vue'
</script>

<template>
  <VBadge
    dot
    location="bottom right"
    offset-x="3"
    offset-y="3"
    color="success"
    bordered
  >
    <div class="d-flex justify-space-between">
      <div class="text-no-wrap text-right mr-3 ml-3">
        <div class="text-subtitle-1">John Dow</div>
        <div class="text-subtitle-2 text-primary">Muster Apotheke 1</div>
      </div>
      <VAvatar
      class="cursor-pointer"
      color="primary"
      variant="tonal"
    >
      <VImg :src="avatar1" />

      <!-- SECTION Menu -->
      <VMenu
        activator="parent"
        width="230"
        location="bottom end"
        offset="14px"
      >
        <ProfileNavItems />
      </VMenu>
      <!-- !SECTION -->
    </VAvatar>
    </div>

  </VBadge>
</template>
