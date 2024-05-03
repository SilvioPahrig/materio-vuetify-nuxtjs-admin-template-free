<script setup lang="ts">
import {useTheme} from 'vuetify'
import {defineProps} from 'vue'

const props = defineProps({
  data: {
    type: Array,
    required: true,
  }
})

const {data} = toRefs(props)

const vuetifyTheme = useTheme()
const visitorsSeries = [
  {
    name: 'Besucher',
    data: data.value.map((item) => item.totalVisiors),
  },
]

const visitorChartOptions = computed(() => {
  const currentTheme = vuetifyTheme.current.value.colors
  return {
    chart: {
      height: 1350,
      type: 'bar',
    },
    colors: [
      currentTheme.info,
      currentTheme.warning,
    ],
    xaxis: {
      categories: data.value.map((item) => item.date),
    },
  }
})
</script>

<template>
  <VCol cols="12" md="8"> <!-- Hier wird die Breite für kleine Bildschirme (md="8") auf 2/3 der Breite gesetzt -->
    <VCard>
      <VCardTitle>Seitenaufrufe der letzten 30 Tage</VCardTitle>
      <VCardText>
        <VueApexCharts
          type="bar"
          :options="visitorChartOptions"
          :series="visitorsSeries"
          :height="250"
          class="my-1"
        />
      </VCardText>
    </VCard>
  </VCol>
</template>

