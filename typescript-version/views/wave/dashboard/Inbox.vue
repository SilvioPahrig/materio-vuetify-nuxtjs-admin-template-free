<script setup lang="ts">
const headers = [
  { title: 'Icon', key: 'icon', width: '50px' },
  { title: 'Title', key: 'title' },
]

const todos = [
  {
    id: 'rezept',
    title: 'keine neuen Rezepte',
    icon: 'ri-receipt-fill',
    color: 'primary',
    link: '/website',
  },
  {
    id: 'bestellung',
    title: 'keine neunen Bestellungen',
    icon: 'ri-shopping-cart-2-fill',
    color: 'primary',
    link: '/eshop',
  },
  {
    id: 'beratungsanfrage',
    title: 'keine neunen Beratungsanfragen',
    icon: 'ri-question-answer-fill',
    color: 'primary',
    link: '/newsletter',
  },
  {
    id: 'kontaktanfrage',
    title: 'keine neuen Kontaktanfragen',
    icon: 'ri-message-fill',
    color: 'primary',
  },
  {
    id: 'chat',
    title: 'keine neuen Chat-Nachrichten',
    icon: 'ri-chat-4-fill',
    color: 'primary',
  },
  {
    id: 'telepharmazie',
    title: 'keine neuen Telepharmazie-Beratungsanfragen',
    icon: 'ri-video-chat-fill',
    color: 'primary',
  },
]

const applyRowColor = ({ index }: { index: number }) => {
  console.log(index)
  return index % 2 === 1 ? 'bg-color-primary' : ''
}
</script>

<template>
  <VCard>
    <VCardItem>
      <VCardTitle>Inbox</VCardTitle>

      <template #append>
        <div class="me-n3">
          <VChip
            color="success"
            size="small"
            class="text-capitalize"
          >
            keine offenen Aufgaben
          </VChip>
        </div>
      </template>
    </VCardItem>

    <VCardText>
      <VDataTable
        :items="todos"
        item-value="id"
        class="text-no-wrap todos-table"
        :headers="headers"
        :item-class="applyRowColor"
      >
        <template #headers />
        <template #bottom />

        <template #item.icon="{ item }">
          <div class="align-center">
            <VIcon
              size="28"
              :icon="item.icon"
              :color="item.color"
            />
          </div>
        </template>
      </VDataTable>
    </VCardText>
  </VCard>
</template>

<style lang="scss">
.todos-table.v-data-table tbody tr:nth-child(even) {
  background-color: #f2f2f2; /* Graue Hintergrundfarbe */
}
</style>
