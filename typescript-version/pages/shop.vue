<script setup>
import Links from "@/views/wave/website/links.vue";
import LinkList from "@/views/wave/LinkList.vue";

const productLinks = [
  {
    title: 'Angebote, Preise & Bestände',
    icon: 'ri-euro-symbol-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/produkte/',

  },
  {
    title: 'Werbung mit Angebotspreisen',
    icon: 'ri-percent-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/streichpreise/',

  },
  {
    title: 'Depotverträge',
    icon: 'ri-assignment-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_allgemein/#href_depot',

  },
  {
    title: 'Eigene Produkte',
    icon: 'ri-insert-photo-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/produkte_apotheke/',

  },
  {
    title: 'Eigene Kategorien',
    icon: 'ri-view-list-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/kategorien_apotheke/',

  },
  {
    title: 'Gutscheine & Rabatte',
    icon: 'ri-card-giftcard-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/gutscheine/',

  },
  {
    title: 'Grundkalkulation eShop',
    icon: 'ri-insert-chart-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_allgemein/#href_kalkulation',

  },
  {
    title: 'Maximale Bestellmenge',
    icon: 'ri-vertical-align-top-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_allgemein/#href_maxbestell',

  },
  {
    title: 'Uploads',
    icon: 'ri-cloud-upload-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/uploads/',

  },
  {
    title: 'Preisvergleiche',
    icon: 'ri-compare-arrows-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/preisvergleiche/',
  }
]

const configLinks = [
  {
    title: 'Reservierung/Abholung',
    icon: 'ri-transfer-within-a-station-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_reservierung/',
  },
  {
    title: 'Botendienst',
    icon: 'ri-directions-car-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_botendienst/',
  },
  {
    title: 'Versand',
    icon: 'ri-local-shipping-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_versand/',
  },
  {
    title: 'Filialen',
    icon: 'ri-place-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_filialen/',
  },
  {
    title: 'Großhandels-Anbindung',
    icon: 'ri-business-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_allgemein/#href_ghanbindung',
  },
  {
    title: 'Rechnungslayout anpassen',
    icon: 'ri-text-rotate-vertical-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_rechnungslayout/',
  },
  {
    title: 'Warenwirtschaft anbinden',
    icon: 'ri-warehouse-line',
    link: 'https://www.wave-cockpit.de/reservierungsshop/einstellungen_warenwirtschaft/',
  },
  {
    title: 'Startseite',
    icon: 'ri-home-line',
    link: 'https://www.wave-cockpit.de/website/inhalte/',
  },
]

const legalLinks = [
  {
    title: 'AGB',
    icon: 'ri-file-list-3-line',
    link: '/apotheke/agb/',
  },
  {
    title: 'Datenschutz',
    icon: 'ri-shield-user-line',
    link: '/apotheke/datenschutz/',
  },
  {
    title: 'Impressum',
    icon: 'ri-information-line',
    link: '/apotheke/impressum/',
  },
  {
    title: 'Widerruf',
    icon: 'ri-arrow-go-back-line',
    link: '/apotheke/widerruf/',
  },
]

const adminLinks = [
  {
    title: 'Website pausieren',
    icon: 'ri-pause-circle-line',
    link: '/apotheke/stop/',
    color: 'error',
  },
]

const mainLinks = [
  {
    title: 'Mein Shop',
    icon: 'ri-macbook-line',
    color: 'info',
    link: 'https://apo2u.com/rosf/',
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
  </VRow>
</template>
