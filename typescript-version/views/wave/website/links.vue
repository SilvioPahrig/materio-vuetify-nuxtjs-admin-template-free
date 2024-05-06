<script setup lang="ts">
import IconButton from '@/views/wave/IconButton.vue'

const statistics = [
  {
    title: 'Meine Webseite',
    icon: 'ri-macbook-line',
    color: 'info',
    link: 'https://apo2u.com/rosf/website/',
    external: true,
  },
  {
    title: 'Kontaktanfrage',
    icon: 'ri-message-line',
    color: 'primary',
    badgeContent: '1',
  },
  {
    title: 'Chat',
    icon: 'ri-message-2-line',
    color: 'primary',
    link: '/chat',
    badgeContent: '2',
  },
]
</script>

<template>
  <VCard>
    <VCardText class="pt-4">
      <VRow>
        <VCol
          v-for="item in statistics"
          :key="item.title"
          cols="6"
          sm="4"
          md="3"
          lg="2"
        >
          <div class="d-flex flex-column align-center justify-center text-center pt-5">
            <template v-if="item.link">
              <RouterLink :to="item.link" v-if="!item.external">
                <IconButton :item="item" />
              </RouterLink>
              <a :href="item.link" target="_blank" rel="noopener noreferrer" v-else>
                <IconButton :item="item" />
              </a>
            </template>
            <div v-else>
              <IconButton :item="item" />
            </div>
          </div>
        </VCol>
      </VRow>
    </VCardText>
  </VCard>
</template>


