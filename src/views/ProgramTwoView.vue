<script setup lang="ts">
import { BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref } from 'vue';
import ProgramItem from '../components/ProgramItem.vue'

const background = new URL('../assets/friday_background.png', import.meta.url).href

// 1. Language State
const currentLang = ref<'en' | 'nl'>('en');

const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

const translations = {
  en: {
    day: "Friday",
    date: "27 February 2026",
    introTitle: "Across a series of panel discussions, we will open conversations on:",
    bullets: [
      "Legislation, moral panic and education, given the current wave of regulation (such as age verification and the prohibition of depicting choking in the UK) and the call to protect the youth. What are the effects of these measures? And what does an effective porn education look like?",
      "Consent, repair and accountability in sex-positive events, film sets and kink spaces. Not as ideals, but as lived, messy practices.",
      "Migrants in the North, from outside the Global North, resist exoticisation and create their own ways for being part and changing the industry."
    ],
    closing: "The day will close with a speed-date, designed to spark exchanges, collaborations and alliances.",
    access: "Industry & Community Day is free for all accredited participants. Companies and members of the general audience are warmly invited to join by purchasing a ticket.",
    lunchInfo: "There is a free drink for everyone, and De Sering offers a vegan lunch for a friendly price.",
    agendaTitle: "Agenda:",
    schedule: [
      "12:00 - 13:00 - Arrival & lunch",
      "13:00 - 14:00 - Legislation, moral panic and education",
      "14:00 - 14:30 - Break",
      "14:30 - 15:30 - Consent, repair and accountability",
      "15:30 - 16:00 - Break",
      "16:00 - 17:00 - Migrants in the North",
      "17:00 - 17:30 - Speed date"
    ],
    prices: [
      "Sex workers and porn creators € 15.00",
      "Companies € 50.00",
      "Visitors € 25.00"
    ]
  },
  nl: {
    day: "Vrijdag",
    date: "27 Februari 2026",
    introTitle: "In drie panelgesprekken snijden we de volgende thema’s aan:",
    bullets: [
      "Wetgeving, morele paniek en educatie. We werpen een blik op de huidige regelementeringsgolf (o.a. leeftijdsverificatie en een verbod op het afbeelden van choking in het VK) en de veelvuldig gehoorde oproep tot bescherming van de jeugd. Welke effecten hebben deze maatregelen? En hoe zou doeltreffende educatie omtrent porno eruit kunnen zien?",
      "Consent, herstel en verantwoordelijkheid op sekspositieve evenementen, filmsets en ruimtes voor kinkbeoefening. Niet als theoretische idealen, maar als werkelijke, doorleefde praktijken die soms ook mis zullen gaan. En wat doe je dan?",
      "Migranten in het Noorden. Over mensen die van buiten het Globale Noorden komen en zich verzetten tegen exoticisme. Hoe banen zij hun eigen paden om deel te kunnen nemen aan de industrie en die misschien ook te veranderen?"
    ],
    closing: "We sluiten de dag af met een speeddate gericht op nieuwe connecties, samenwerkingen en uitwisseling van ideeën.",
    access: "Industry & Community Day is gratis toegankelijk met accreditatie. Bedrijven en festivalbezoekers zijn zeer welkom om deel te nemen door een toegangskaartje te kopen.",
    lunchInfo: "Er is voor iedereen een gratis drankje, en de Sering biedt een veganistische lunch aan voor een vriendelijke prijs.",
    agendaTitle: "Rooster:",
    schedule: [
      "12:00 - 13:00 - Inloop & lunch",
      "13:00 - 14:00 - Wetgeving, morele paniek en educatie",
      "14:00 - 14:30 - Pauze",
      "14:30 - 15:30 - Consent, herstel en verantwoordelijkheid",
      "15:30 - 16:00 - Pauze",
      "16:00 - 17:00 - Migranten in het Noorden",
      "17:00 - 17:30 - Speeddate"
    ],
    prices: [
      "Sekswerkers en pornomakers € 15.00",
      "Bedrijven € 50.00",
      "Bezoekers € 25.00"
    ]
  }
};

const agenda = [
  {
    "id": 1,
    "image": new URL('../assets/ic1.png', import.meta.url).href,
    "title": "Industry & Community Day",
    "time": "12:00 - 17:30",
    "place": "De Sering",
    "text": {
      "en": "Porn Film Festival Amsterdam was founded on the belief that porn is not disposable content, but a core part of culture. It is made by people, shaped by politics, economies, migration, desire, censorship and care. If porn is to thrive as an artistic and political practice, it needs spaces where those who create it can meet, reflect, disagree, repair and imagine new futures together.<br/><br/>For this edition, we invite filmmakers, performers, content creators, sex workers, activists and allies to come together around the questions that ground our work: How do we make porn ethically and sustainably? How do we navigate power, consent and care across sets, screens and sex-positive spaces?",
      "nl": "Porn Film Festival Amsterdam is opgericht met de overtuiging dat porno geen wegwerpartikel, maar een wezenlijk deel van onze cultuur is. Het is mensenwerk dat wordt beïnvloed door lust, zorg, politiek, economie en migratie. Als porno wil kunnen floreren als een artistieke en politiek praktijk, zijn er ontmoetingsplekken nodig waarin makers van gedachten kunnen wisselen, het oneens mogen zijn, herstellend werk kunnen verrichten en samen nieuwe toekomstbeelden mogen bedenken.<br/><br/>Voor deze editie nodigen we filmmakers, performers, content creators, sekswerkers, activisten en bondgenoten uit om vragen te bespreken die aan de basis van ons werk liggen: Hoe maken we porno ethisch en duurzaam? Hoe gaan we om met macht, consent en zorg op de set, op het scherm en in sekspositieve ruimtes?"
    },
    "description": "",
    "duration": "",
    "imagelogo": new URL('../assets/DeSering-Logo.png', import.meta.url).href,
    "ticket": "https://amsterdamalternative.nl/tickets/20917"
  }
]
</script>

<template>
  <b-container fluid
  class="d-flex flex-column min-vh-100 px-0 view-background"
  :style="{ 
    backgroundImage: 'url(' + background + ')',
    backgroundSize: 'cover',
    backgroundPosition: 'center',
    backgroundRepeat: 'no-repeat',
    backgroundAttachment: 'fixed'
  }">
    
    <b-row class="mt-5">
      <b-col xs="12" class="text-center">
        <div class="titles mt-5">{{ translations[currentLang].day }}</div>
        <div class="titles">{{ translations[currentLang].date }}</div>
      </b-col>
    </b-row>

    <b-row class="justify-content-center my-4">
      <b-col cols="auto" class="d-flex align-items-center">
        <span class="lang-label me-2" :class="{ 'active-lang': currentLang === 'nl' }">NL</span>
        <b-form-checkbox 
          :model-value="currentLang === 'en'" 
          @change="toggleLang" 
          switch 
          size="lg"
          class="custom-switch"
        />
        <span class="lang-label ms-2" :class="{ 'active-lang': currentLang === 'en' }">ENG</span>
      </b-col>
    </b-row>

    <program-item 
        v-for="(item, index) in agenda" 
        :key="item.id" 
        :image="item.image"
        :title="item.title"
        :time="item.time"
        :place="item.place"
        :description="item.description"
        :duration="item.duration"
        :text="item.text[currentLang]"
        :imagelogo="item.imagelogo"
        :ticket="item.ticket"
        :reverse="index % 2 !== 0"
        :is-first="index === 0"
    />

    <b-row class="mx-5 px-5">
      <b-col xs="12" lg="8" class="mx-4">
        <br/>
        <div class="mb-3"><strong>{{ translations[currentLang].introTitle }}</strong></div>
        
        <ul class="mb-4">
          <li v-for="(bullet, i) in translations[currentLang].bullets" :key="i" class="mb-3">
            {{ bullet }}
          </li>
        </ul>
        
        <div class="mb-3">{{ translations[currentLang].closing }}</div>
        <div class="mt-4">{{ translations[currentLang].access }}</div>
        <div class="mt-2"><i>{{ translations[currentLang].lunchInfo }}</i></div>
      </b-col>
    </b-row>

    <b-row class="mx-5 px-5 mt-4">
      <b-col xs="12" lg="6" class="mx-4">
        <h4 style="font-weight: bold;">{{ translations[currentLang].agendaTitle }}</h4>
        <br/>
        <div v-for="(line, i) in translations[currentLang].schedule" :key="i" class="mb-1">
          {{ line }}
        </div>
      </b-col>
    </b-row>

    <b-row class="mx-5 px-5 mt-4 pb-5">
      <b-col xs="12" lg="6" class="mx-4">
        <div v-for="(price, i) in translations[currentLang].prices" :key="i" class="mb-1">
          {{ price }}
        </div>
      </b-col>
    </b-row>

  </b-container>
</template>

<style scoped>
.lang-label {
  font-weight: bold;
  color: #555;
  font-family: sans-serif;
}

.active-lang {
  color: #000;
}

:deep(.form-check-input) {
  cursor: pointer;
  background-color: #6a4da1 !important;
  border-color: #6a4da1 !important;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'%3e%3ccircle r='3' fill='%23fff'/%3e%3c/svg%3e") !important;
}

:deep(.form-check-input:checked) {
  background-color: #6a4da1 !important;
}

.titles {
  font-size: 3em;
  font-weight: bold;
}

@media (max-width: 576px) {
  .titles {
    font-size: 1.5em;
  }
}
</style>