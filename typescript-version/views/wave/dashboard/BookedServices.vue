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
    link: '/eshop',
  },
  {
    title: 'Newsletter',
    icon: 'ri-mail-line',
    color: 'primary',
    link: '/newsletter',
  },
  {
    title: 'Chat',
    icon: 'ri-message-2-line',
    color: 'primary',
  },
  {
    title: 'Impfzentrum',
    icon: 'ri-syringe-line',
    color: 'primary',
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
          <div class="d-flex flex-column align-center justify-center">
            <VAvatar
              :color="item.color"
              rounded
              size="40"
              class="elevation-1"
            >
              <VIcon
                size="24"
                :icon="item.icon"
              />

            </VAvatar>

            <div class="text-center">
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
