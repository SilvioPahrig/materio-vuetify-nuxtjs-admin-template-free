<script setup lang="ts">
import {useTheme} from 'vuetify'
import {hexToRgb} from '@layouts/utils'

let data = []
let daysInThePast = 30

for (let i = 0; i < daysInThePast; i++) {
  let date = new Date(Date.now() - i * 24 * 60 * 60 * 1000)
  let formattedDate = `${String(date.getDate()).padStart(2, '0')}.${String(date.getMonth() + 1).padStart(2, '0')}.`

  let orderCount = Math.floor(Math.random() * 15) + 4
  let totalAmount = 0
  for (let j = 0; j < orderCount; j++) {
    totalAmount += Math.floor(Math.random() * 88) + 8
  }
  data.push({
    'date': formattedDate,
    'orderCount': orderCount, // Ersetzen Sie dies durch die tatsächlichen Daten
    'totalAmount': totalAmount, // Ersetzen Sie dies durch die tatsächlichen Daten
  })
}

data = data.reverse();

const vuetifyTheme = useTheme()

const series = [
  {
    name: 'Umsatz',
    data: data.map((item) => item.totalAmount),
  },
  {
    name: 'Bestllungen',
    data: data.map((item) => item.orderCount),
  },
]

const chartOptions = computed(() => {
  const currentTheme = vuetifyTheme.current.value.colors

  return {
    chart: {
      id: 'vuechart-example',
    },
    colors: [
      currentTheme.info,
      currentTheme.warning,
    ],
    xaxis: {
      categories: data.map((item) => item.date),
    },
    yaxis: [
      {
        title: {
          text: 'Umsatz',
        },
        labels: {
          formatter: function (value) {
            return value + ' €' // Fügt die Einheit Euro an den Wert an
          },
        },
      },
      {
        opposite: true,
        title: {
          text: 'Bestellungen',
        },
      },
    ],
  }
})
</script>

<template>
  <VCard>
    <VCardItem>
      <VCardTitle>Umsatz der letzten 30 Tage</VCardTitle>
    </VCardItem>
    <VCardText>
      <VRow>
        <VCol cols="12" md="4"> <!-- Hier wird die Breite für kleine Bildschirme (md="4") auf 1/3 der Breite gesetzt -->
          <VCard>
            <VCardTitle>
              <h6>Vom {{ data[0].date }} bis {{ data[data.length - 1].date}}{{ (new Date(Date.now())).getFullYear() }}</h6></VCardTitle>
            <VCardText>
              <VList>
                <VListItem>
                  <div class="d-flex align-center gap-x-3">
                    <VAvatar
                      color="info"
                      rounded
                      size="40"
                      class="elevation-2"
                    >
                      <VIcon
                        size="24"
                        icon="ri-money-dollar-circle-line"
                      />
                    </VAvatar>

                    <div class="d-flex flex-column">
                      <div class="text-body-1">
                        Umsatz
                      </div>
                      <h5 class="text-h5">
                        {{ data.reduce((sum, item) => sum + item.totalAmount, 0).toLocaleString('de-DE') }},00 €
                      </h5>
                    </div>
                  </div>
                </VListItem>
                <VListItem class="mt-4">
                  <div class="d-flex align-center gap-x-3">
                    <VAvatar
                      color="warning"
                      rounded
                      size="40"
                      class="elevation-2"
                    >
                      <VIcon
                        size="24"
                        icon="ri-shopping-cart-2-line"
                      />
                    </VAvatar>

                    <div class="d-flex flex-column">
                      <div class="text-body-1">
                        Anzahl Bestellungen
                      </div>
                      <h5 class="text-h5">
                        {{ data.reduce((sum, item) => sum + item.orderCount, 0) }}
                      </h5>
                    </div>
                  </div>
                </VListItem>

                <VListItem class="mt-4">
                  <div class="d-flex align-center gap-x-3">
                    <VAvatar
                      color="primary"
                      rounded
                      size="40"
                      class="elevation-2"
                    >
                      <VIcon
                        size="24"
                        icon="ri-user-3-line"
                      />
                    </VAvatar>

                    <div class="d-flex flex-column">
                      <div class="text-body-1">
                        Neukunden Bestellungen
                      </div>
                      <h5 class="text-h5">
                        {{ Math.floor(Math.random() * 15) + 4 }}
                      </h5>
                    </div>
                  </div>
                </VListItem>
              </VList>
            </VCardText>
          </VCard>
        </VCol>
        <VCol cols="12" md="8">
          <VCard>
            <VCardText>
              <VueApexCharts
                type="line"
                :options="chartOptions"
                :series="series"
                :height="240"
                class="my-1"
              />
            </VCardText>
          </VCard>
        </VCol>
      </VRow>
    </VCardText>
  </VCard>
</template>

