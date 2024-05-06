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
const totalOrders = computed(() => {
  if (Array.isArray(data.value)) {
    return data.value.reduce((sum, item) => sum + item.orderCount, 0)
  }
  return 0
})
const vuetifyTheme = useTheme()
const series = computed(() => [
  Math.round(totalOrders.value * 0.37),
  Math.round(totalOrders.value * 0.42),
  Math.round(totalOrders.value * 0.21),
])

const chartOptions = computed(() => {
  const currentTheme = vuetifyTheme.current.value.colors
  return {
    chart: {
      width: 380,
      type: 'pie',
    },
    colors: [
      currentTheme.info,
      currentTheme.warning,
      currentTheme.success,
    ],
    labels: ['Abholung', 'Botendienst', 'Versand'],
    responsive: [{
      breakpoint: 480,
      options: {
        chart: {
          width: 380,
        },
        legend: {
          position: 'bottom'
        }
      }
    }],
    dataLabels: {
      formatter: function(val, opts) {
        return opts.w.globals.series[opts.seriesIndex]
      }
    }
  }
})
</script>

<template>
  <VCol cols="12" md="4"> <!-- Hier wird die Breite für kleine Bildschirme (md="8") auf 2/3 der Breite gesetzt -->
    <VCard>
      <VCardItem>
      <VCardTitle>Bestellungen nach Versandtyp</VCardTitle>
      </VCardItem>
      <VCardText>
        <VueApexCharts
          type="pie"
          :options="chartOptions"
          :series="series"
          width="380"
        />
      </VCardText>
    </VCard>
  </VCol>
</template>

