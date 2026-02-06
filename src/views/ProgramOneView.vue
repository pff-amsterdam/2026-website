<script setup lang="ts">
import { BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref } from 'vue'; 
import ProgramItem from '../components/ProgramItem.vue'

const background = new URL('../assets/thursday_background.png', import.meta.url).href

// 1. Language State
const currentLang = ref<'en' | 'nl'>('en');

const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

const translations = {
  en: { day: "Thursday", date: "26 February 2026" },
  nl: { day: "Donderdag", date: "26 Februari 2026" }
};

const agenda = [
{
  "id": 1,
  "image": new URL('../assets/thursday1.png', import.meta.url).href,
  "title": "CHEEKY SNEAK PEEK",
  "time": "16:00",
  "place": "Filmhuis CAVIA",
  "text": {
    "en": "A very sneaky welcome to Porn Film Festival Amsterdam 2026. To start off this edition with a bang (yes), we invite you to peek around the corner with us at Filmhuis Cavia. Get a glimpse of some of our darlings and a quick tour through several of the themes of this year’s program. Whether you’re a first-timer or a regular, this selection is sure to whet your appetite and leave you begging for what’s to come.",
    "nl": "Een zeer sneaky welkom op Porn Film Festival Amsterdam 2026. Als opzwepend begin van deze derde editie nodigen we je uit om over de klapdeurtjes van Filmhuis Cavia heen te gluren en alvast een glimp op te vangen van het programma dat je te wachten staat. Met een greep uit onze persoonlijke favorieten leiden we je langs de thema’s van deze editie. Of je nu een nieuwkomer of een trouwe bezoeker bent, deze boeiende selectie zal je doen smeken om meer films."
  },
  "description": `<p>
    <strong>Thing</strong> | Ori Di Vincenzo | 2024 | Germany | 11’
    <br/>
    <strong>The Eternal Whore. Regulation of sex work through history</strong> | Rori Dior, Diego Gómez | 2024 | Germany | 11’
    <br/>
    <strong>Feverish</strong> | Fabienne Garçonne & Jamal Phoenix | 2025 | Switzerland | 5'
    <br/>
    <strong>Glimmer</strong> | Fennek Film | 2025 | Sweden | 2'
    <br/>
    <strong>Your REAL Companion</strong> | Officer Flower, Iris Glitzer | 2025 | Germany | 13’
    <br/>
    <strong>Mating Season</strong> | Juan Saez / Heavy Load Studio | 2025 | Germany | 9’
    <br/>
    <strong>alt.sex.fetish.robots</strong> | Zed Sheng | 2025 | USA, Thailand | 5’
    <br/>
    <strong>Blue Movie</strong> | dw zero | 2025 | Greece | 1’
    <br/>
    <strong>TARANTA TARANTA</strong> | Kiki Kazimi, Lola Pistola | 2025 | Italy | 5’
    <br/>
    <strong>Fluister voor me</strong> | Silkyway's Universe | 2025 | Netherlands | 4’
    <br/>
    <strong>Ravine</strong> | Oat Montien | 2024 | USA | 6’
    <br/>
    <strong>French Breads</strong> | Mathieu Berthon | 2025 | France | 17’
    <br/>
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 89 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 89 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20881"
},
{
  "id": 2,
  "image": new URL('../assets/thursday2.png', import.meta.url).href,
  "title": "CRUISING (Beyond) THE WORLD",
  "time": "18:00",
  "place": "Filmhuis CAVIA",
  "text": {
    "en": "Cruising lives in the space between wanting and being wanted. It’s the hunt, the heat, the glance that lingers a second too long. A ritual born from survival and desire, a way of finding each other in the dark, in the margins, in the places not meant for us. These films trace bodies in motion: circling, seeking, inviting. They explore risk, play, power and the quiet language of strangers who meet without words.",
    "nl": "Cruising vindt plaats in de ruimte tussen begeren en begeerd worden. Het is een verhitte jacht, een blik die net iets te lang blijft hangen, een ritueel dat ontsproot uit overleving en verlangen. Een manier om elkaar te vinden in het donker, in de marges, op plekken die niet voor ons bedoeld waren. Deze films tonen lichamen in beweging: rondcirkelend, speurend, verwelkomend. Ze nemen risico’s, spelen met macht en de geruisloze taal van vreemden in een woordeloze ontmoeting."
  },
  "description": `<p>
    <strong>Cybersex 19</strong> | Chico Ludermir | 2024 | Brazil | 9’
    <br/>
    <strong>Hijos de Hímero (Sons of Himeros)</strong> | Santiago Calle G. | 2025 | Colombia | 16’
    <br/>
    <strong>A Garden Under The Earth</strong> | Pedro Lavin | 2024 | USA, Mexico | 6’
    <br/>
    <strong>The Gnoll Hole Patrol</strong> | Monsterbait & Xavours | 2025 | France | 6’
    <br/>
    <strong>Cumrags</strong> | Blade | 2025 | Germany | 16’
    <br/>
    <strong>( CON - TACTOS )</strong> | Julu Martínez | 2024 | Spain | 7’
    <br/>
    <strong>French Breads</strong> | Mathieu Berthon | 2025 | France | 17’
    <br/>
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 77 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 77 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/agenda/20884"
},
  {
    "id": 3,
    "image": new URL('../assets/thursday3.png', import.meta.url).href,
    "title": "OPENING PARTY",
    "time": "21:00",
    "place": "Vrankrijk",
    "text": {
      "en": "Climb out of your cold caves, leave your dark alleys, throw off those socks and blankets, this party will warm you up in no time. We’ll inaugurate the third edition of the festival with steamy performances and smooth DJ’s that will make you hot and hungry for more.",
      "nl": "Kruip je koude kelder uit, kom uit die donkere steeg tevoorschijn, gooi je wollen sokken en je dekentje in een hoek, want dit feest warmt je in een mum van tijd op. We luiden de derde editie van het festival in met vlammende performances en onze vurige DJ’s maken je heet en hongerig naar meer."
    },
    "description": ``,
    "duration": "",
    "imagelogo": new URL('../assets/Vrankrijk.png', import.meta.url).href,
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
      <b-col xs="12" lg="12" class="text-center">
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
        :duration="item.duration ? item.duration[currentLang] : ''"
        :text="item.text[currentLang]"
        :imagelogo="item.imagelogo"
        :ticket="item.ticket"
        :reverse="index % 2 !== 0"
        :is-first="index === 0"
    />
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
  border-color: #6a4da1 !important;
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