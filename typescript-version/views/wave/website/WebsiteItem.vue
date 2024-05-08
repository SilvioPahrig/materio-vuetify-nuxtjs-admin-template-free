<template>
  <div :id="'item-' + item.id" class="outer-wrapper" @mouseover="isHovered = true" @mouseleave="isHovered = false">
    <div class="d-flex justify-space-between" :class="{ 'hovered': isHovered }">
      <label class="d-flex align-center">
        <VCheckbox v-model="selected" @change="updateSelection" class="ml-2"></VCheckbox><span class="font-weight-bold">{{ item.title }}</span>
      </label>

      <div class="d-flex align-center">
        <VIcon v-if="item.editable" @click="edit = !edit">ri-pencil-line</VIcon>
        <VIcon v-if="item.configable" @click="edit = !edit">ri-settings-3-line</VIcon>
        <VIcon v-else></VIcon>
        <VDivider class="ml-3 mr-2" :thickness="2" vertical/>
        <VIcon>ri-arrow-down-s-line</VIcon>
        <VIcon>ri-arrow-up-s-line</VIcon>
      </div>
    </div>
    <VCard v-if="hasEditSlot && edit" variant="tonal" class="edit-item ma-2">
      <VCardTitle>Bearbeitungsmodus: {{ item.title }}</VCardTitle>
      <VCardText>
        <slot name="edit"></slot>
      </VCardText>
    </VCard>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      isHovered: false,
      selected: this.item.selected,
      edit: false,
    }
  },
  methods: {
    updateSelection(newValue) {
      this.item.selected = newValue;
      this.$emit('update:item', this.item);
    },
  },
  computed: {
    // Überprüfe, ob der benannte Slot `content` gesetzt ist
    hasEditSlot(): boolean {
      return !!this.$slots.edit;
    },
  },
})

</script>

<style scoped>
.outer-wrapper {
  cursor: pointer; /* So dass der Cursor seine Form ändert, wenn er über das Element schwebt */
}

.outer-wrapper .hovered {
  background-color: #ccc; /* Grauer Hintergrund beim Schweben über das Element */
}

.edit-item {
  width: 90%;
}
</style>
