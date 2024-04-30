<script setup lang="ts">
import BookedServices from "@/views/wave/dashboard/BookedServices.vue";
import Inbox from "@/views/wave/dashboard/Inbox.vue";
import DazNews from "@/views/wave/dashboard/DazNews.vue";
</script>

<template>
  <VRow class="match-height">
    <VCol cols="12">
      <BookedServices />
    </VCol>
    <VCol cols="12">
      <Inbox />
    </VCol>
    <VCol cols="12">
      <DazNews />
    </VCol>
  </VRow>
</template>
