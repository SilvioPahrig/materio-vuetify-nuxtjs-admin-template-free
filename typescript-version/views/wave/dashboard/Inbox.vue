<script setup lang="ts">
const headers = [
  { title: 'Icon', key: 'icon', width: '50px' },
  { title: 'Title', key: 'title' },
]

const todos = [
  {
    id: 'rezept',
    count: 2,
    singular: 'ein neues Rezept',
    plural: 'Rezepte',
    icon: 'ri-receipt-fill',
    color: 'primary',
    link: '/website',
  },
  {
    id: 'bestellung',
    count: 6,
    singular: 'eine neue Bestellung',
    plural: 'Bestellungen',
    icon: 'ri-shopping-cart-2-fill',
    color: 'primary',
    link: '/eshop',
  },
  {
    id: 'beratungsanfrage',
    count: 1,
    singular: 'eine neue Beratungsanfrage',
    plural: 'Beratungsanfragen',
    icon: 'ri-question-answer-fill',
    color: 'primary',
    link: '/newsletter',
  },
  {
    id: 'kontaktanfrage',
    count: 1,
    singular: 'eine neue Kontaktanfrage',
    plural: 'Kontaktanfragen',
    icon: 'ri-message-fill',
    color: 'primary',
  },
  {
    id: 'chat',
    count: 2,
    singular: 'eine neue Chat-Nachricht',
    plural: 'Chat-Nachrichten',
    icon: 'ri-chat-4-fill',
    color: 'primary',
  },
  {
    id: 'telepharmazie',
    count: 2,
    singular: 'eine neuen Telepharmazie-Beratungsanfrage',
    plural: 'Telepharmazie-Beratungsanfragen',
    icon: 'ri-video-chat-fill',
    color: 'primary',
  },
]

const totalTodos = computed(() => {
  return todos.reduce((acc, todo) => acc + todo.count, 0)
});

const getItemColor = (count) => {
  return count === 0 ? 'success' : 'warning'
};



const applyRowColor = ({ index }: { index: number }) => {
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
            :color="getItemColor(totalTodos)"
            size="small"
          >
            {{ totalTodos === 0 ? 'Keine offenen Aufgaben' : totalTodos === 1 ? 'Eine offene Aufgabe' : totalTodos + ' offene Aufgaben' }}
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

        <template #item.title="{ item }">

          <span>
            {{ item.count === 0 ? 'keine offenen ' + item.plural : item.count === 1 ? item.singular : item.count + ' offene ' + item.plural }}
          </span>

        </template>

        <template #item.icon="{ item }">
          <div class="position-relative">
            <VIcon
              size="28"
              :icon="item.icon"
              :color="getItemColor(item.count)"
            />
            <VChip
              :color="getItemColor(item.count)"
              size="small"
              class="position-absolute top-0 end-0 ml-n3 mt-n2 z-index-1"
            >
              {{ item.count }}
            </VChip>
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
