<script lang="ts" setup>
import { defineProps, toRefs } from "vue";

const props = defineProps({
  items: {
    type: Array,
    required: true,
  },
});

const { items } = toRefs(props)

const headers = [
  { title: 'Title', key: 'title' },
]
</script>

<template>
  <VDataTable
    :items="items"
    item-value="id"
    class="text-no-wrap todos-table"
    :headers="headers"
  >
    <template #headers />
    <template #bottom />

    <template #item.title="{ item }">
      <RouterLink v-if="item.to" :to=item.to>
        <VIcon
          size="28"
          style="margin-right: 30px;"
          :icon="item.icon"
          :color="item.color ? item.color : secondary"
        />
        <span :class="'text-' + item.color">{{ item.title }}</span>
      </RouterLink>
      <div v-else class="nav-link">
        <VIcon
          size="28"
          style="margin-right: 30px;"
          :icon="item.icon"
          :color="item.color ? item.color : secondary"
        />
        <span :class="'text-' + item.color">{{ item.title }}</span>
      </div>
    </template>
  </VDataTable>
</template>
