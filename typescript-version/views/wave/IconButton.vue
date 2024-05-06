<script lang="ts" setup>
import {defineProps} from "vue";

const props = defineProps({
  item: {
    type: Array,
    required: true,
  },
})

const { item } = toRefs(props)

</script>

<template>
  <VAvatar
    :color="item.color"
    rounded
    size="72"
    class="elevation-1"
  >
    <VIcon
      size="48"
      :icon="item.icon"
    />
    <!-- Verwendung von v-badge -->
    <VBadge
      v-if="item.badgeContent"
      color="error"
      overlap
      left
      offset-y="-20"
      offset-x="2"
    >
      <template #badge>{{ item.badgeContent }}</template>
    </VBadge>
  </VAvatar>
  <div class="text-center pa-3">
    <div class="text-body-1">
      {{ item.title }}
    </div>
  </div>
</template>
