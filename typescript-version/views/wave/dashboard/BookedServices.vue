<script setup lang="ts">
import IconButton from '@/views/wave/IconButton.vue'

const statistics = [
  {
    title: 'Webseite',
    icon: 'ri-macbook-line',
    color: 'primary',
    link: '/website',
  },
  {
    title: 'eShop',
    icon: 'ri-shopping-cart-2-line',
    color: 'primary',
    link: '/shop',
  },
  {
    title: 'Newsletter',
    icon: 'ri-mail-line',
    color: 'primary',
  },
  {
    title: 'Chat',
    icon: 'ri-message-2-line',
    color: 'primary',
    link: '/chat',
    badgeContent: '2',
  },
  {
    title: 'Impfzentrum',
    icon: 'ri-syringe-line',
    color: 'primary',
    link: '/vaccination-center',
  },
  {
    title: 'Telepharmazie Free',
    icon: 'ri-live-line',
    color: 'primary',
  },
]
</script>

<template>
  <VCard title="Gebuchte Leistungen">
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
          <div class="d-flex flex-column align-center justify-center text-center">
            <RouterLink v-if="item.link" :to="item.link">
            <IconButton :item="item" />
            </RouterLink>
            <div v-else>
              <IconButton :item="item" />
            </div>
          </div>
        </VCol>
      </VRow>
    </VCardText>
  </VCard>
</template>
