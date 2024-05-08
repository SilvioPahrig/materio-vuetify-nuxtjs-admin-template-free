<template>
  <VRow>
    <VCol cols="12">
      <VCard>
        <VCardItem>
          <VCardTitle>Startseite</VCardTitle>
        </VCardItem>
        <VCardSubtitle>Wählen Sie die gewünschten Elemente für Ihre Startseite aus.</VCardSubtitle>
        <VCardText>
          <WebsiteItem :item="{ id: 1, title: 'Einleitung', editable: true, configable: false, selected: true }"
                       @update:item="updateItem(index, $event)">
            <template #edit>
              <VTextarea outlined rows="5"
                         placeholder="Hier können Sie eine Einleitung für Ihre Startseite eingeben."></VTextarea>
            </template>
          </WebsiteItem>
          <WebsiteItem :item="{ id: 2, title: 'Öffnungszeiten', editable: false, configable: true, selected: true }"
                       @update:item="updateItem(index, $event)">
            <template #edit>
              <VCardItem>
                <table cellspacing="10">
                  <thead>
                  <tr>
                    <th width="180">Wochentag</th>
                    <th>von</th>
                    <th>bis</th>
                  </tr>
                  </thead>
                  <tbody>
                  <tr>
                    <td>
                      <VSelect
                        label="Wochentag"
                        :items="['Mo-Fr', 'Montag', 'Dienstag', 'Mittwoch', 'Donnerstag', 'Freitag', 'Samstag', 'Sonntag']"
                      />
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <VSelect
                        label="Wochentag"
                        :items="['Mo-Fr', 'Montag', 'Dienstag', 'Mittwoch', 'Donnerstag', 'Freitag', 'Samstag', 'Sonntag']"
                      />
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <VSelect
                        label="Wochentag"
                        :items="['Mo-Fr', 'Montag', 'Dienstag', 'Mittwoch', 'Donnerstag', 'Freitag', 'Samstag', 'Sonntag']"
                      />
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <VSelect
                        label="Wochentag"
                        :items="['Mo-Fr', 'Montag', 'Dienstag', 'Mittwoch', 'Donnerstag', 'Freitag', 'Samstag', 'Sonntag']"
                      />
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                    <td>
                      <VTextField type="time"></VTextField>
                    </td>
                  </tr>
                  </tbody>
                </table>
              </VCardItem>
            </template>
          </WebsiteItem>
          <WebsiteItem
            :item="{ id: 3, title: 'Produktempfehlungen', editable: false, configable: false, selected: true }"
            @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 4, title: 'Shop-Kategorien', editable: false, configable: false }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 5, title: 'Chat', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)">
            <template #edit>
              <VCardItem class="v-field--variant-solo mb-4">
                <VCardTitle>Benachrichtigungen</VCardTitle>
                <VCardSubtitle>Hier stellen Sie ein, ob und über welche Kanäle Sie bei neuen Chat-Nachrichten benachrichtigt werden wollen.</VCardSubtitle>
                <VDivider class="my-4" />
                <div>Dazu wechseln Sie bitte zu <b>Einstellungen</b> > <span class="text-primary">Benachrichtigungen</span></div>
              </VCardItem>
              <VCardItem class="v-field--variant-solo mb-4">
                <VCardTitle>Antwortzeit</VCardTitle>
                <VCardSubtitle>Geben Sie an, wie schnell Sie im Durchschnitt (während Ihrer Öffnungszeiten) auf neue Chatnachrichten reagieren können. Diese Angabe wird dem Endkunden im Chatfenster angezeigt.</VCardSubtitle>
                <VDivider class="my-4" />
                <div><VSelect style="max-width: 250px"
                  label="Antwortzeit"
                  :items="['unmittelbar', '30 Minuten', '1 Stunde', '2 Stunden', '4 Stunden', 'innerhalb eines Tages']"
                /></div>
               </VCardItem>
              <VCardItem class="v-field--variant-solo mb-4">
                <VCardTitle>Chat pausieren</VCardTitle>
                <VCardSubtitle>Schaltet Ihren Chat aus. Daten oder Einstellungen gehen nicht verloren. Eine Aktivierung ist jederzeit wieder möglich.</VCardSubtitle>
                <VDivider class="my-4" />
                <div class="text-primary"><VCheckbox color="error" label="Chat pausieren"></VCheckbox></div>
               </VCardItem>
            </template>
          </WebsiteItem>
          <WebsiteItem
            :item="{ id: 6, title: 'Newsletter-Formular', editable: false, configable: true, selected: true }"
            @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 7, title: 'Positionierung', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 8, title: 'my life', editable: false, configable: false }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 9, title: 'Stellenangebote', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem
            :item="{ id: 10, title: 'Gesundheitsratgeber', editable: false, configable: false, selected: true }"
            @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 11, title: 'Gutschein-Slider', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 12, title: 'Hersteller-Slider', editable: false, configable: false }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 13, title: 'Kosmetik-Sortiment', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 14, title: 'Aktionen und Veranstaltungen', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 15, title: 'Corona-Impfung', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 16, title: 'Grippe-Impfung', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 17, title: 'Karte', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 18, title: 'Team', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 19, title: 'Individueller Inhalt', editable: true, configable: false }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 20, title: 'ABDA-Kampagnen', editable: false, configable: false }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 21, title: 'IA Widget', editable: false, configable: false }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>
          <WebsiteItem :item="{ id: 22, title: 'Leistungen', editable: false, configable: true }"
                       @update:item="updateItem(index, $event)"></WebsiteItem>


        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>

<script lang="ts" setup>
import WebsiteItem from "@/views/wave/website/WebsiteItem.vue";

const updateItem = (index, newItem) => {
};

</script>
