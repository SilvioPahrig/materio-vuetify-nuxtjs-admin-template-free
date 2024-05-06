<script setup lang="ts">
import IconButton from '@/views/wave/IconButton.vue'
import {defineProps, toRefs} from "vue";

const props = defineProps({
  links: {
    type: Array,
    required: true,
  },
});

const {links} = toRefs(props)

</script>

<template>
  <VRow>
    <VCol
      v-for="item in links"
      :key="item.title"
      cols="6"
      sm="4"
      md="3"
      lg="2"
    >
      <div class="d-flex flex-column align-center justify-center text-center pt-5">
        <template v-if="item.link">
          <RouterLink :to="item.link" v-if="!item.external">
            <IconButton :item="item"/>
          </RouterLink>
          <a :href="item.link" target="_blank" rel="noopener noreferrer" v-else>
            <IconButton :item="item"/>
          </a>
        </template>
        <div v-else>
          <IconButton :item="item"/>
        </div>
      </div>
    </VCol>
  </VRow>
</template>


