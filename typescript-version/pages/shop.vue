<script setup>
import Links from "@/views/wave/website/links.vue";
import LinkList from "@/views/wave/LinkList.vue";

const productLinks = [
  {
    title: 'Angebote, Preise & Bestände',
    icon: 'ri-money-euro-circle-line',
  },
  {
    title: 'Werbung mit Angebotspreisen',
    icon: 'ri-discount-percent-line',

  },
  {
    title: 'Depotverträge',
    icon: 'ri-contract-line',

  },
  {
    title: 'Eigene Produkte',
    icon: 'ri-image-fill',

  },
  {
    title: 'Eigene Kategorien',
    icon: 'ri-list-check',

  },
  {
    title: 'Gutscheine & Rabatte',
    icon: 'ri-gift-line',

  },
  {
    title: 'Grundkalkulation eShop',
    icon: 'ri-bar-chart-box-line',

  },
  {
    title: 'Maximale Bestellmenge',
    icon: 'ri-skip-up-line',

  },
  {
    title: 'Uploads',
    icon: 'ri-upload-cloud-2-line',

  },
  {
    title: 'Preisvergleiche',
    icon: 'ri-arrow-left-right-line',
  },
]

const configLinks = [
  {
    title: 'Reservierung/Abholung',
    icon: 'ri-walk-line',
  },
  {
    title: 'Botendienst',
    icon: 'ri-car-line',
  },
  {
    title: 'Versand',
    icon: 'ri-truck-line',
  },
  {
    title: 'Filialen',
    icon: 'ri-map-pin-line',
  },
  {
    title: 'Großhandels-Anbindung',
    icon: 'ri-building-line',
  },
  {
    title: 'Rechnungslayout anpassen',
    icon: 'ri-edit-box-line',
  },
  {
    title: 'Warenwirtschaft anbinden',
    icon: 'ri-bank-line',
  },
  {
    title: 'Startseite',
    icon: 'ri-home-4-line',
  },
]

const legalLinks = [
  {
    title: 'AGB',
    icon: 'ri-survey-line',
  },
  {
    title: 'Datenschutz',
    icon: 'ri-shield-check-line',
  },
  {
    title: 'Impressum',
    icon: 'ri-information-line',
  },
  {
    title: 'Widerruf',
    icon: 'ri-arrow-go-back-line',
  },
  {
    title: 'Archiv Bestellungen (Aufbewahrungspflicht)',
    icon: 'ri-archive-2-line',
  },
]

const adminLinks = [
  {
    title: 'Shop pausieren',
    icon: 'ri-pause-circle-line',
    color: 'error',
  },
]

const mainLinks = [
  {
    title: 'Mein Shop',
    icon: 'ri-macbook-line',
    color: 'info',
    link: 'https://fancy-sprinkles-7a5789.netlify.app/category?0',
    external: true,
  },
  {
    title: 'Bestellungen',
    icon: 'ri-shopping-cart-line',
    color: 'primary',
    badgeContent: '6',
  },
  {
    title: 'Rezepte',
    icon: 'ri-file-list-3-line',
    color: 'primary',
    badgeContent: '2',
  },
  {
    title: 'Beratungsanfragen',
    icon: 'ri-questionnaire-line',
    color: 'primary',
    badgeContent: '1',
  },
  {
    title: 'Kontaktanfragen',
    icon: 'ri-message-line',
    color: 'primary',
    badgeContent: '1',
  },
  {
    title: 'Chat-Anfragen',
    icon: 'ri-chat-1-line',
    color: 'primary',
    badgeContent: '2',
  },
  {
    title: 'Kundendaten',
    icon: 'ri-user-line',
    color: 'primary',
  },
]
</script>

<template>
  <VRow>
    <VCol cols="12">
      <VCard>
        <VCardItem>
          <VCardTitle>Mein Shop</VCardTitle>
        </VCardItem>
      </VCard>
    </VCol>
    <VCol cols="12">
      <VCard>
        <VCardTitle>Bestellungen & Kundenanfragen</VCardTitle>
        <VCardSubtitle>Aktuelle Bestellungen, Rezepte und Anfragen.</VCardSubtitle>
        <VCardText>
          <Links :links="mainLinks"/>
        </VCardText>
      </VCard>
    </VCol>
    <VCol cols="12" md="6">
      <VCard>
        <VCardTitle>Preise & Produkte</VCardTitle>
        <VCardSubtitle>Alles rund um Preise und Produkte.</VCardSubtitle>
        <VCardText>
          <LinkList :items="productLinks"/>
        </VCardText>
      </VCard>
    </VCol>
    <VCol cols="12" md="6">
      <VCard>
        <VCardTitle>Allgemeine Einstellungen</VCardTitle>
        <VCardSubtitle>Verwalten Sie hier die Einstellungen Ihres eShops.</VCardSubtitle>
        <VCardText>
          <LinkList :items="configLinks"/>
        </VCardText>
      </VCard>
    </VCol>
    <VCol cols="12" md="6">
      <VCard>
        <VCardTitle>Rechtliches</VCardTitle>
        <VCardSubtitle>Alle rechtlich relevanten Informationen auf einem Blick.</VCardSubtitle>
        <VCardText>
          <LinkList :items="legalLinks"/>
        </VCardText>
      </VCard>
    </VCol>
    <VCol cols="12" md="6">
      <VCard>
        <VCardTitle>Admin Einstellungen</VCardTitle>
        <VCardSubtitle>Verwalten Sie Ihren eShop.</VCardSubtitle>
        <VCardText>
          <LinkList :items="adminLinks"/>
        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>
