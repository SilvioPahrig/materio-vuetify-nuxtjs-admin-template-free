<template>
  <div :id="'item-' + item.id" class="outer-wrapper" @mouseover="isHovered = true" @mouseleave="isHovered = false">
    <div class="d-flex justify-space-between" :class="{ 'hovered': isHovered }">
      <label class="d-flex align-center">
        <VCheckbox v-model="selected" @change="updateSelection" class="ml-2"></VCheckbox><span class="font-weight-bold">{{ item.title }}</span>
      </label>

      <div class="d-flex align-center">
        <VIcon v-if="item.editable">ri-pencil-line</VIcon>
        <VIcon v-if="item.configable">ri-settings-3-line</VIcon>
        <VIcon v-else></VIcon>
        <VDivider class="ml-3 mr-2" :thickness="2" vertical/>
        <VIcon>ri-arrow-down-s-line</VIcon>
        <VIcon>ri-arrow-up-s-line</VIcon>
      </div>
    </div>
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
    }
  },
  methods: {
    updateSelection(newValue) {
      this.localItem.selected = newValue;
      this.$emit('update:item', this.localItem);
    },
  },
});
</script>

<style scoped>
.outer-wrapper {
  cursor: pointer; /* So dass der Cursor seine Form ändert, wenn er über das Element schwebt */
}

.outer-wrapper .hovered {
  background-color: #ccc; /* Grauer Hintergrund beim Schweben über das Element */
}
</style>
