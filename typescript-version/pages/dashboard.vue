<script setup lang="ts">
import BookedServices from "@/views/wave/dashboard/BookedServices.vue";
import Inbox from "@/views/wave/dashboard/Inbox.vue";
</script>

<template>
  <VRow class="match-height">
    <VCol cols="12">
      <BookedServices />
    </VCol>
    <VCol cols="12">
      <Inbox />
    </VCol>
  </VRow>
</template>
