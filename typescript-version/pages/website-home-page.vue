<template>
  <VRow>
    <VCol cols="12">
      <VCard>
        <VCardItem>
          <VCardTitle>Startseite</VCardTitle>
        </VCardItem>
        <VCardSubtitle>Wählen Sie die gewünschten Elemente für Ihre Startseite aus.</VCardSubtitle>
        <VCardText>
          <WebsiteItem v-for="(item, index) in websiteItems" :key="index" :item="item" @update:item="updateItem(index, $event)" />
        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>

<script lang="ts" setup>
import WebsiteItem from "@/views/wave/website/WebsiteItem.vue";

const updateItem = (index, newItem) => {
  websiteItems[index] = newItem;
};

const websiteItems = [
  { id: 1, title: "Einleitung", editable: true, configable: false, selected: true },
  { id: 2, title: "Öffnungszeiten", editable: false, configable: true, selected: true },
  { id: 3, title: "Produktempfehlungen", editable: false, configable: false, selected: true },
  { id: 4, title: "Shop-Kategorien", editable: false, configable: false },
  { id: 5, title: "Chat", editable: false, configable: true },
  { id: 6, title: "Newsletter-Formular", editable: false, configable: true, selected: true },
  { id: 7, title: "Positionierung", editable: false, configable: true },
  { id: 8, title: "my life", editable: false, configable: false },
  { id: 9, title: "Stellenangebote", editable: false, configable: true },
  { id: 10, title: "Gesundheitsratgeber", editable: false, configable: false, selected: true },
  { id: 11, title: "Gutschein-Slider", editable: false, configable: true },
  { id: 12, title: "Hersteller-Slider", editable: false, configable: false },
  { id: 13, title: "Kosmetik-Sortiment", editable: false, configable: true },
  { id: 14, title: "Aktionen und Veranstaltungen", editable: false, configable: true },
  { id: 15, title: "Corona-Impfung", editable: false, configable: true },
  { id: 16, title: "Grippe-Impfung", editable: false, configable: true },
  { id: 17, title: "Karte", editable: false, configable: true },
  { id: 18, title: "Team", editable: false, configable: true },
  { id: 19, title: "Individueller Inhalt", editable: true, configable: false },
  { id: 20, title: "ABDA-Kampagnen", editable: false, configable: false },
  { id: 21, title: "IA Widget", editable: false, configable: false },
  { id: 22, title: "Leistungen", editable: false, configable: true },
];

</script>
