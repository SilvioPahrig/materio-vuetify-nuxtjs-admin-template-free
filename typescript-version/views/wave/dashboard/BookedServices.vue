<script setup lang="ts">
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
    link: '/dashboard',
  },
  {
    title: 'Chat',
    icon: 'ri-message-2-line',
    color: 'primary',
    link: '/chat',
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
    link: '/dashboard',
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
          <div class="d-flex flex-column align-center justify-center">
            <router-link :to="item.link">
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

            </VAvatar>
            </router-link>

            <div class="text-center pa-3">
              <div class="text-body-1">
                {{ item.title }}
              </div>
            </div>

          </div>
        </VCol>
      </VRow>
    </VCardText>
  </VCard>
</template>
