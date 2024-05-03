<script setup lang="ts">
import BookedServices from '@/views/wave/dashboard/BookedServices.vue'
import Inbox from '@/views/wave/dashboard/Inbox.vue'
import DazNews from '@/views/wave/dashboard/DazNews.vue'
import TotalAmount from '@/views/wave/dashboard/TotalAmount.vue'
import TotalUser from '@/views/wave/dashboard/TotalUser.vue'
import OrderByShipping from '@/views/wave/dashboard/OrderByShipping.vue'

const data = []
const daysInThePast = 30

for (let i = 0; i < daysInThePast; i++) {
  const date = new Date(Date.now() - i * 24 * 60 * 60 * 1000)
  const formattedDate = `${String(date.getDate()).padStart(2, '0')}.${String(date.getMonth() + 1).padStart(2, '0')}.`

  const orderCount = Math.floor(Math.random() * 15) + 4
  let totalAmount = 0
  for (let j = 0; j < orderCount; j++) {
    totalAmount += Math.floor(Math.random() * 88) + 8
  }
  data.push({
    date: formattedDate,
    orderCount: orderCount,
    totalAmount: totalAmount,
    totalVisiors: Math.floor(Math.random() * 200) + 77,
  })
}
data.reverse()

</script>

<template>
  <VRow class="match-height">
    <VCol cols="12">
      <BookedServices />
    </VCol>
    <VCol cols="12">
      <TotalAmount :data="data" />
    </VCol>
    <TotalUser :data="data"/>
    <OrderByShipping :data="data"/>
    <VCol cols="12">
      <Inbox />
    </VCol>
    <VCol cols="12">
      <DazNews />
    </VCol>
  </VRow>
</template>
