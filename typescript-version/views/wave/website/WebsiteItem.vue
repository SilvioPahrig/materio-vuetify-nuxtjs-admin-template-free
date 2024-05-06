<template>
  <div class="d-flex justify-space-between">
    <label class="d-flex align-center">
      <VCheckbox v-model="isChecked" class="ml-2"></VCheckbox>
      <span class="font-weight-bold">{{ title }}</span>
    </label>

    <div class="d-flex align-center">
      <VIcon v-if="editable">ri-pencil-line</VIcon>
      <VIcon v-if="configable">ri-settings-3-line</VIcon>
      <VIcon v-else></VIcon>
      <VDivider class="ml-3 mr-2" :thickness="2" vertical/>
      <VIcon>ri-arrow-down-s-line</VIcon>
      <VIcon>ri-arrow-up-s-line</VIcon>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    id: {
      type: Number,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    configable: {
      type: Boolean,
      default: true,
    },
    editable: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      isChecked: false,
    }
  },
}
</script>
