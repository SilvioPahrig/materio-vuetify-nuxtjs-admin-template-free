<script setup>
import WebsiteItem from "@/views/wave/website/WebsiteItem.vue";
</script>

<template>
  <VContainer>

    <WebsiteItem title="Notdienst">
      <template #description>
        Website Inhalte für Notdienste
      </template>
    </WebsiteItem>
    <WebsiteItem title="Öffnungszeiten" :configable=false>
      <template #description>
        <section class="container" id="openings">
          <div>
            <h2 class="mt-0">Öffnungszeiten</h2>
            <div class="openings-hint mb-2 opened">Jetzt geöffnet: <span>09:00 Uhr - 18:30 Uhr</span></div>
            <div class="read-more-wrapper show-less">
              <div class="openings"><div class="openings__block" data-day="1"><div class="openings__block__day">Mo</div><div class="openings__block__time"><span>09:00 - 18:30 Uhr</span></div></div><div class="openings__block" data-day="2"><div class="openings__block__day">Di</div><div class="openings__block__time"><span>09:00 - 18:30 Uhr</span></div></div><div class="openings__block" data-day="3"><div class="openings__block__day">Mi</div><div class="openings__block__time"><span>09:00 - 18:30 Uhr</span></div></div><div class="openings__block openings__block--opened" data-day="4"><div class="openings__block__day">Do</div><div class="openings__block__time"><span>09:00 - 18:30 Uhr</span></div></div><div class="openings__block" data-day="5"><div class="openings__block__day">Fr</div><div class="openings__block__time"><span>09:00 - 18:30 Uhr</span></div></div><div class="openings__block" data-day="6"><div class="openings__block__day">Sa</div><div class="openings__block__time"><span>08:00 - 13:30 Uhr</span></div></div></div>				<div class="read-more color-brand-lighter"><a href="#" class="btn btn--link btn--xs btn--icon-right">mehr anzeigen<span class="icon icon--size-16 icon--right icon--x-arrow-down-link"></span></a></div>
            </div>
            <p class="t-large"><strong>Nicht geöffnet?</strong> Finden Sie hier eine &nbsp;&nbsp;&nbsp;<a class="btn btn--flat mt-0-5" href="https://m.aponet.de/notdienstsuche.html?no-sensor=54.18004525_7.88536210118069&amp;address=helgoland" title="Finden Sie hier die heutige Notdienstapotheke in Ihrer Nähe!">Notdienstapotheke in Ihrer Nähe! <span class="icon icon--size-20 icon--right icon--x-add-circle-outline-alert"></span> </a></p>
          </div>
        </section>
      </template>
    </WebsiteItem>
    <WebsiteItem
      title="test"
      :editable=false
    >
      <template #description>
        <b>Apple iPhone 12</b> Pro smartphone. Announced Sep 2019. Features 5.8″ display Apple A13 Bionic
      </template>
    </WebsiteItem>
  </VContainer>
</template>
