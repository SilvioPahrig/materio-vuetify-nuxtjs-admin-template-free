<script setup lang="ts">
// import axios from 'axios'

const newsItems = ref([])
const feed = `<?xml version="1.0" encoding="utf-8"?>
<rss version="2.0" xmlns:atom="http://www.w3.org/2005/Atom" xmlns:content="http://purl.org/rss/1.0/modules/content/" xmlns:media="http://search.yahoo.com/mrss/">
  <channel>
    <title>DAZ.online Tagesnews</title>
    <link>http://www.deutsche-apotheker-zeitung.de</link>
    <description>Aktuelle Tagesnews - Deutsche Apotheker Zeitung'</description>
    <atom:link href="https://www.deutsche-apotheker-zeitung.de/xml/news.rss2" rel="self" type="application/rss+xml"/>
    <image>
      <title>DAZ.online Tagesnews</title>
      <link>http://www.deutsche-apotheker-zeitung.de</link>
      <url>https://www.deutsche-apotheker-zeitung.de/_Resources/Static/Packages/CRON.DazSite/images/DAZ_Logo.png</url>
    </image>
    <item>
      <title>Vierteilige Online-Fortbildung: E-Rezept-Gipfel 2024 startet</title>
      <pubDate>Tue, 30 Apr 2024 07:00:00 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/30/e-rezept-gipfel-2024-startet</link>
      <description><![CDATA[Seit Anfang des Jahres hat das E-Rezept das Muster 16 ersetzt. Immer wieder kommt es zu technischen Problemen. Am heutigen Dienstag startet eine vierteilige Online-Fortbildung: der E-Rezept-Gipfel.]]></description>
      <content:encoded><![CDATA[Seit Anfang des Jahres hat das E-Rezept das Muster 16 ersetzt. Immer wieder kommt es zu technischen Problemen. Am heutigen Dienstag startet eine vierteilige Online-Fortbildung: der E-Rezept-Gipfel.]]></content:encoded>
      <enclosure length="30507" type="image/jpg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/b/0/d/7/b0d70877848d25e3baedce19d21677f41e8ce700/imago0391657820h-3825x2153-400x225.jpg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/b/0/d/7/b0d70877848d25e3baedce19d21677f41e8ce700/imago0391657820h-3825x2153-400x225.jpg" fileSize="30507" type="image/jpg" medium="image"/>
      <guid isPermaLink="false">53c7a780-ecef-4ab2-a0ea-6e14ead05824</guid>
    </item>
    <item>
      <title>Mustervereinbarung steht: KÃ¼nftig Honorar fÃ¼r den Sichtbezug?</title>
      <pubDate>Tue, 30 Apr 2024 07:00:00 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/30/kuenftig-honorar-fuer-den-sichtbezug</link>
      <description><![CDATA[Der Deutsche Apothekerverband hat sich mit dem AOK-Bundesverband auf eine Mustervereinbarung Ã¼ber den Sichtbezug in Apotheken geeinigt. Sie sieht unter anderem ein Honorar von 5,49 Euro je verordneter...]]></description>
      <content:encoded><![CDATA[Der Deutsche Apothekerverband hat sich mit dem AOK-Bundesverband auf eine Mustervereinbarung Ã¼ber den Sichtbezug in Apotheken geeinigt. Sie sieht unter anderem ein Honorar von 5,49 Euro je verordneter...]]></content:encoded>
      <enclosure length="30364" type="image/jpg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/6/6/7/e/667e77d79823646457d42a814ab002e9897f25e3/9184654-3504x1970-400x225.jpg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/6/6/7/e/667e77d79823646457d42a814ab002e9897f25e3/9184654-3504x1970-400x225.jpg" fileSize="30364" type="image/jpg" medium="image"/>
      <guid isPermaLink="false">4d8a7638-d95d-42e4-82af-924500cc2dc8</guid>
    </item>
    <item>
      <title>Apokix-Umfrage: Nachwuchs als â€žwichtigste Investitionâ€œ</title>
      <pubDate>Mon, 29 Apr 2024 17:50:00 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/29/nachwuchs-als-wichtigste-investition</link>
      <description><![CDATA[Bei der Suche nach Nachwuchs sehen sich die Apotheken vor spezielle Probleme gestellt. Mit welchen Herausforderungen sie kÃ¤mpfen und was sie dagegen tun, das geht aus der jÃ¼ngsten Apokix-Umfrage hervo...]]></description>
      <content:encoded><![CDATA[Bei der Suche nach Nachwuchs sehen sich die Apotheken vor spezielle Probleme gestellt. Mit welchen Herausforderungen sie kÃ¤mpfen und was sie dagegen tun, das geht aus der jÃ¼ngsten Apokix-Umfrage hervo...]]></content:encoded>
      <enclosure length="54084" type="image/jpg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/4/f/9/f/4f9f7c8c06870b00b7d5aad3943b4b1cb7f6b168/PTAheute_DAZ_Apothekenshooting2024_3736-1080x607-400x225.jpg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/4/f/9/f/4f9f7c8c06870b00b7d5aad3943b4b1cb7f6b168/PTAheute_DAZ_Apothekenshooting2024_3736-1080x607-400x225.jpg" fileSize="54084" type="image/jpg" medium="image"/>
      <guid isPermaLink="false">2def0620-b5dd-4306-9150-36943d48b1c9</guid>
    </item>
    <item>
      <title>Gefahr fÃ¼r Menschen?: USA: Vogelgrippe bei KÃ¼hen Ã¼berrascht Virologen</title>
      <pubDate>Mon, 29 Apr 2024 16:45:46 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/29/vogelgrippe-bei-kuehen-ueberrascht-virologen-gefahr-fuer-menschen</link>
      <description><![CDATA[Das Vogelgrippevirus befÃ¤llt weltweit immer mehr SÃ¤ugetiere. Nun hat es KÃ¼he in den USA erreicht und damit Nutztiere, mit denen viele Menschen Kontakt haben. Welche Gefahren birgt das? Die Weltgesundh...]]></description>
      <content:encoded><![CDATA[Das Vogelgrippevirus befÃ¤llt weltweit immer mehr SÃ¤ugetiere. Nun hat es KÃ¼he in den USA erreicht und damit Nutztiere, mit denen viele Menschen Kontakt haben. Welche Gefahren birgt das? Die Weltgesundh...]]></content:encoded>
      <enclosure length="200017" type="image/jpeg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/f/8/3/0/f830e9c728326fb0103071913f051fa221749780/Kuh_Milch_AdobeStock_572496635_Editorial_Use_Only_Kristina%20Blokhin-6000x3373-400x225.jpeg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/f/8/3/0/f830e9c728326fb0103071913f051fa221749780/Kuh_Milch_AdobeStock_572496635_Editorial_Use_Only_Kristina%20Blokhin-6000x3373-400x225.jpeg" fileSize="200017" type="image/jpeg" medium="image"/>
      <guid isPermaLink="false">3299e73f-7cb3-4e01-ad66-f386d6fe3e8d</guid>
    </item>
    <item>
      <title>â€žWir sehen rotâ€œ: ABDA wertet Protestkampagne als Erfolg</title>
      <pubDate>Mon, 29 Apr 2024 16:45:00 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/29/abda-bewertet-protestkampagne-als-erfolg</link>
      <description><![CDATA[Die ABDA-Kampagne â€žWir sehen rotâ€œ endete am vergangenen Samstag. In zahlreichen Medien fanden die Protestaktionen GehÃ¶r. ABDA-PrÃ¤sidentin Overwiening spricht von einem Erfolg. Es sei gelungen, die Pat...]]></description>
      <content:encoded><![CDATA[Die ABDA-Kampagne â€žWir sehen rotâ€œ endete am vergangenen Samstag. In zahlreichen Medien fanden die Protestaktionen GehÃ¶r. ABDA-PrÃ¤sidentin Overwiening spricht von einem Erfolg. Es sei gelungen, die Pat...]]></content:encoded>
      <enclosure length="33355" type="image/jpg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/4/9/1/5/491553fa8a5101eb033d7f8e45a2f6e1c60ef660/wir%20sehen%20rot%20bild-1591x895-400x225.jpg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/4/9/1/5/491553fa8a5101eb033d7f8e45a2f6e1c60ef660/wir%20sehen%20rot%20bild-1591x895-400x225.jpg" fileSize="33355" type="image/jpg" medium="image"/>
      <guid isPermaLink="false">3cceab8b-b318-4ebd-8711-7582869314dd</guid>
    </item>
    <item>
      <title>Arzneimittelkommission der deutschen Apotheker / ChargenrÃ¼ckruf: OeKolpÂ® forte Ovula 0,5 mg VaginalzÃ¤pfchen, 20 StÃ¼ck</title>
      <pubDate>Mon, 29 Apr 2024 15:54:10 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/amk-meldungen/2024/04/29/oekolp-forte-ovula-0-5-mg-vaginalzaepfchen-20-stueck</link>
      <description><![CDATA[OeKolp<sup>Â®</sup> forte Ovula 0,5 mg VaginalzÃ¤pfchen&nbsp;<br>20 StÃ¼ck&nbsp;<br>Ch.-B.: 23000333]]></description>
      <content:encoded><![CDATA[OeKolp<sup>Â®</sup> forte Ovula 0,5 mg VaginalzÃ¤pfchen&nbsp;<br>20 StÃ¼ck&nbsp;<br>Ch.-B.: 23000333]]></content:encoded>
      <guid isPermaLink="false">c8b7eca7-833d-44d2-8d75-f1b5faa890a8</guid>
    </item>
    <item>
      <title>â€žUN-Diktatorâ€œ und Aufweichung des Patentschutzes: Offene Streitpunkte erschweren Abschluss des WHO-Pandemievertrags</title>
      <pubDate>Mon, 29 Apr 2024 15:00:00 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/29/offene-streifpunkte-erschweren-abschluss-des-who-pandemievertrag</link>
      <description><![CDATA[Die Weltgesundheitsorganisation plant einen globalen Pandemievertrag. Er soll die nationalen Gesundheitssysteme und die pharmazeutische Industrie besser fÃ¼r zukÃ¼nftige pandemische Notsituationen wappn...]]></description>
      <content:encoded><![CDATA[Die Weltgesundheitsorganisation plant einen globalen Pandemievertrag. Er soll die nationalen Gesundheitssysteme und die pharmazeutische Industrie besser fÃ¼r zukÃ¼nftige pandemische Notsituationen wappn...]]></content:encoded>
      <enclosure length="32461" type="image/jpg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/1/6/e/5/16e58294a3d290148c7089e82a0ae526114ec66a/imago0397997752h-3968x2231-400x225.jpg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/1/6/e/5/16e58294a3d290148c7089e82a0ae526114ec66a/imago0397997752h-3968x2231-400x225.jpg" fileSize="32461" type="image/jpg" medium="image"/>
      <guid isPermaLink="false">8e5b3855-1173-4c1f-ad5e-4935803b8968</guid>
    </item>
    <item>
      <title>Sphingosin-1-Phosphat-Rezeptor-Modulator: Etrasimod gegen Colitis ulcerosa â€“ neu in Deutschland verfÃ¼gbar</title>
      <pubDate>Mon, 29 Apr 2024 13:45:00 +0200</pubDate>
      <link>https://www.deutsche-apotheker-zeitung.de/news/artikel/2024/04/29/etrasimod-in-deutschland-verfuegbar</link>
      <description><![CDATA[FÃ¼r Patienten und Patientinnen mit Colitis ulcerosa steht ein neues orales Arzneimittel zur VerfÃ¼gung: Ein PrÃ¤parat mit&nbsp;</span><span>Etrasimod ist nach der Zulassung im Februar 2024 nun in Deutsc...]]></description>
      <content:encoded><![CDATA[FÃ¼r Patienten und Patientinnen mit Colitis ulcerosa steht ein neues orales Arzneimittel zur VerfÃ¼gung: Ein PrÃ¤parat mit&nbsp;</span><span>Etrasimod ist nach der Zulassung im Februar 2024 nun in Deutsc...]]></content:encoded>
      <enclosure length="12402" type="image/jpg" url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/c/0/9/9/c09915ab62d861668f4c3f73c035fc6ea23df817/Clipboard01-708x398-400x225.jpg"/>
      <media:content url="https://www.deutsche-apotheker-zeitung.de/_Resources/Persistent/c/0/9/9/c09915ab62d861668f4c3f73c035fc6ea23df817/Clipboard01-708x398-400x225.jpg" fileSize="12402" type="image/jpg" medium="image"/>
      <guid isPermaLink="false">ff324e16-56b5-4e1a-a42b-a0a96ba81bf5</guid>
    </item>
  </channel>
</rss>`

// q: wie kann ich die sonderzeichen in feed berichtigen

const fixSpecialCharacters = (feed) => {
  return feed.replace(/Ã¼/g, 'ü')
    .replace(/Ã¶/g, 'ö')
    .replace(/Ã¤/g, 'ä')
    .replace(/ÃŸ/g, 'ß')
    .replace(/Ã„/g, 'Ä')
    .replace(/Ã–/g, 'Ö')
    .replace(/Ãœ/g, 'Ü')
    .replace(/â€ž/g, '„')
    .replace(/â€œ/g, '“')
}

const removeHtmlTags = (text) => {
  return text.replace(/<[^>]*>?/gm, '');
}

// Funktion zum Abrufen des RSS-Feeds und Speichern der Nachrichtenobjekte
const getRSSFeed = () => {
  return fixSpecialCharacters(feed)
  // https://www.deutsche-apotheker-zeitung.de/xml/news.rss2
}
const parseRSSFeed = (feed) => {
  // Hier sollte die Logik zum Abrufen des RSS-Feeds implementiert werden, zum Beispiel mit fetch() oder einer anderen Methode
  const parser = new DOMParser();
  const xmlDoc = parser.parseFromString(feed, 'text/xml');

  const items = xmlDoc.getElementsByTagName('item');
  const news = [];

  for (let i = 0; i < items.length; i++) {
    const title = items[i].getElementsByTagName('title')[0].textContent;
    const pubDate = items[i].getElementsByTagName('pubDate')[0].textContent;
    const description = removeHtmlTags(items[i].getElementsByTagName('description')[0].textContent);
    const link = items[i].getElementsByTagName('link')[0].textContent;
    const mediaContent = items[i].getElementsByTagName('media:content');
    const image = mediaContent.length > 0 ? mediaContent[0].getAttribute('url') : null;

    news.push({ title, pubDate, description, link, image });
  }

  return news;
}

// RSS-Feed abrufen und Nachrichten laden, wenn die Komponente montiert ist
onMounted(() => {
  const rssfeed = getRSSFeed()
  newsItems.value = parseRSSFeed(rssfeed);
})
</script>

<template>
  <VRow>
    <VCol
      v-for="(item, index) in newsItems"
      :key="index"
      sm="6"
      cols="12"
    >
      <VCard>
        <div class="d-flex justify-space-between flex-wrap flex-md-nowrap flex-column flex-md-row">
          <div class="ma-auto pa-5">
            <template v-if="item.image">
              <VImg
                width="137"
                height="176"
                :src="item.image"
                alt="News Image"
              />
            </template>
            <template v-else>
              <div
                class="d-flex justify-center align-center"
                style="width: 137px; height: 176px;"
              >
                <i class="ri-gallery-line" style="font-size: 96px;"></i>
              </div>
            </template>
          </div>

          <VDivider :vertical="$vuetify.display.mdAndUp" />

          <div>
            <VCardItem>
              <VCardTitle>{{ item.title }}</VCardTitle>
            </VCardItem>

            <VCardText>{{ item.description }}</VCardText>

            <VCardText class="text-subtitle-1">
              <span>{{ item.pubDate }}</span>
            </VCardText>

            <VCardActions class="justify-space-between">
              <VBtn
                color="primary"
                :href="item.link"
                target="_blank"
              >
                <VIcon icon="ri-arrow-right-s-line" />
                <span class="ms-2">Read more</span>
              </VBtn>
            </VCardActions>
          </div>
        </div>
      </VCard>
    </VCol>
  </VRow>
</template>
