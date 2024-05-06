<script setup>
import Links from "@/views/wave/website/links.vue";
import LinkList from "@/views/wave/LinkList.vue";

const pageLinks = [
{
    title: 'Startseite',
    icon: 'ri-home-4-line',
    link: '/website/home/',
},
{
    title: 'Seiten',
    icon: 'ri-window-line',
    link: '/website/pages/',
},
{
    title: 'Startseiten-Slider',
    icon: 'ri-carousel-view',
    link: '/website/slider/',
},
{
    title: 'Aktionen',
    icon: 'ri-calendar-event-line',
    link: '/events/',
},
{
    title: 'Stellenangebote',
    icon: 'ri-group-line',
    link: '/job-offers/',
},
{
    title: 'Außenansicht',
    icon: 'ri-image-2-line',
    link: '/pharmacy/exterior/',
},
{
    title: 'Team',
    icon: 'ri-team-line',
    link: '/pharmacy/team/',
},
{
    title: 'Service & Leistungen',
    icon: 'ri-tools-line',
    link: '/pharmacy/service/',
},
]

const apoLinks = [
  {
    title: 'Adresse & Kontaktdaten',
    icon: 'ri-map-pin-line',
    link: '/apotheke/adresse/',
  },
  {
    title: 'Benachrichtigungen',
    icon: 'ri-notification-3-line',
    link: '/apotheke/benachrichtigungen/',
  },
  {
    title: 'Domain',
    icon: 'ri-earth-line',
    link: '/apotheke/domain/',
  },
  {
    title: 'Layout & Logo',
    icon: 'ri-palette-line',
    link: '/apotheke/optik/',
  },
  {
    title: 'Öffnungszeiten',
    icon: 'ri-time-line',
    link: '/apotheke/oeffnungszeiten/',
  },
  {
    title: 'Positionierungen',
    icon: 'ri-bubble-chart-line',
    link: '/apotheke/positionierung/',
  },
  {
    title: 'Statistik',
    icon: 'ri-line-chart-line',
    link: '/apotheke/statistiken/',
  },
  {
    title: 'Selbstdarstellung',
    icon: 'ri-information-line',
    link: '/apotheke/selbstdarstellung/',
  },
  {
    title: 'Social Media',
    icon: 'ri-share-line',
    link: '/apotheke/social_media/',
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
    title: 'Meine Webseite',
    icon: 'ri-macbook-line',
    color: 'info',
    link: 'https://apo2u.com/rosf/website/',
    external: true,
  },
  {
    title: 'Kontaktanfrage',
    icon: 'ri-message-line',
    color: 'primary',
    badgeContent: '1',
  },
  {
    title: 'Chat',
    icon: 'ri-message-2-line',
    color: 'primary',
    link: '/chat',
    badgeContent: '2',
  },
]

</script>

<template>
  <VRow>
    <VCol cols="12">
      <VCard>
        <VCardItem>
          <VCardTitle>Meine Website</VCardTitle>
        </VCardItem>
      </VCard>
    </VCol>
    <VCol cols="12">
      <VCard>
        <VCardText class="pt-4">
      <Links :links="mainLinks"/>
        </VCardText>
      </VCard>
    </VCol>
  <VCol cols="12" md="6">
    <VCard>
      <VCardTitle>Inhalte</VCardTitle>
      <VCardSubtitle>Verwalten Sie hier die Inhalte und Einstellungen Ihrer Website.</VCardSubtitle>
      <VCardText>
      <LinkList :items="pageLinks"/>
      </VCardText>
    </VCard>
  </VCol>
    <VCol cols="12" md="6">
      <VCard>
        <VCardTitle>Meine Apotheke</VCardTitle>
        <VCardSubtitle>Hier finden Sie alle wichtigen Einstellungen für Ihre Apotheke.</VCardSubtitle>
        <VCardText>
          <LinkList :items="apoLinks"/>
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
        <VCardSubtitle>Verwalten Sie Ihre Website.</VCardSubtitle>
        <VCardText>
          <LinkList :items="adminLinks"/>
        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>
