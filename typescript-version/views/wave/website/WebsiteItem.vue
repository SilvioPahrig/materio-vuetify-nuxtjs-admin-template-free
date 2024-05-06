<template>
  <VRow>
    <VCol cols="12">
      <VCard>
        <VCardItem>
          <VCardTitle class="d-flex justify-space-between align-center">
            {{ title }}
            <div class="d-flex align-center">
              <VIcon v-if="editable">ri-pencil-line</VIcon>
              <VIcon v-if="configable">ri-settings-3-line</VIcon>
              <VIcon v-else></VIcon>
              <VDivider class="ml-3 mr-2" :thickness="2" vertical/>
              <VIcon>ri-arrow-down-s-line</VIcon>
              <VIcon>ri-arrow-up-s-line</VIcon>
            </div>
          </VCardTitle>
        </VCardItem>

        <VSpacer class="py-2" />
        <VCardText>
          <slot name="description"></slot>
        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>

<script>
export default {
  props: {
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
  }
}
</script>
