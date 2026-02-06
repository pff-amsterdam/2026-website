<script setup lang="ts">
import { BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref } from 'vue';

const background = new URL('../assets/extra_background.png', import.meta.url).href
const currentLang = ref<'en' | 'nl'>('en');

const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

const translations = {
  en: {
    // ... (Keep existing About Us translations here)
    accessibilityTitle: "Accessibility",
    accessibilityLinks: [
      { text: "Accessibility statement", url: "https://docs.google.com/document/d/1dFRrpxl4gGUw-_mBFsOByd-WPzqCdoWH2DtjwuOsX2o/edit?tab=t.0" },
      { text: "Accessibility request form", url: "https://docs.google.com/forms/d/e/1FAIpQLScljgbUzu6q7sTXo22GhvxDg5onJYWQD5TbEOsz0-LjNaYHlQ/viewform" }
    ],
    ticketsTitle: "Tickets & prices",
    ticketsPrice: "Tickets: 7 euros",
    workshopsPrice: "Workshops: 15 euros",
    cineville: "Cineville card accepted",
    presale: "Presale for screenings and workshops:",
    ticketInfo: "Each day there will be a limited number of tickets available at the bar of the two cinemas. You can get them on the day and location of the screening itself. Cineville cards are accepted at both locations.",
    venueTitle: "Venue info",
    venueUrl: "https://docs.google.com/document/d/1_D5hEGY3FLelMLJt6GZhYgBp8qMMuhM5adr5KXeBzcg/edit?tab=t.0#heading=h.8fsdd0or3jdd",
    venueSub: "Venue measurements and information for accessibility",
    triggerTitle: "Stance on trigger warnings",
    triggerText: [
      "Everyone is turned on, touched, or triggered by different things. What feels playful or hot to one person might feel confronting to another. That’s part of why we use porn as a space for storytelling, desire, protest and expanding perspective.",
      "Sometimes it’s joyful. Sometimes it’s uncomfortable.",
      "Rather than traditional trigger warnings, this year we invite you into a moment of self check-in before each screening. Take a breath and ask yourself: do I feel safe right now? Am I open to discovering something new, even if it brings discomfort? Or do I feel more in need of protection?",
      "If it’s the latter, honour that. Maybe you sit closer to the exit. Maybe you line up someone to talk to afterwards. There’s no right way to show up, just an invitation to arrive consciously, with care for yourself and others.",
      "Each block will be introduced by the programmer to give context. And if you have specific questions or needs, you’re always welcome to reach out to us on Instagram or in person."
    ]
  },
  nl: {
    // ... (Add Dutch translations for the new sections here)
    accessibilityTitle: "Toegankelijkheid",
    accessibilityLinks: [
      { text: "Toegankelijkheidsverklaring", url: "https://docs.google.com/document/d/1dFRrpxl4gGUw-_mBFsOByd-WPzqCdoWH2DtjwuOsX2o/edit?tab=t.0" },
      { text: "Aanvraagformulier toegankelijkheid", url: "https://docs.google.com/forms/d/e/1FAIpQLScljgbUzu6q7sTXo22GhvxDg5onJYWQD5TbEOsz0-LjNaYHlQ/viewform" }
    ],
    ticketsTitle: "Tickets & prijzen",
    ticketsPrice: "Tickets: 7 euro",
    workshopsPrice: "Workshops: 15 euro",
    cineville: "Cineville kaart geaccepteerd",
    presale: "Voorverkoop voor voorstellingen en workshops:",
    ticketInfo: "Elke dag is er een beperkt aantal kaarten beschikbaar aan de bar van de twee bioscopen. Je kunt deze op de dag en locatie van de vertoning zelf kopen. Cineville-kaarten worden op beide locaties geaccepteerd.",
    venueTitle: "Locatie info",
    venueUrl: "https://docs.google.com/document/d/1_D5hEGY3FLelMLJt6GZhYgBp8qMMuhM5adr5KXeBzcg/edit?tab=t.0#heading=h.8fsdd0or3jdd",
    venueSub: "Afmetingen van de locatie en informatie over toegankelijkheid",
    triggerTitle: "Standpunt over trigger warnings",
    triggerText: [ /* Dutch version of trigger text */ ]
  }
};

const venues = [
  {
    name: "FILMHUIS CAVIA",
    address: "Van Hallstraat 52-I 1051 HH Amsterdam",
    transport: "Tram 3 · Van Hallstraat (last stop)\nBus 21 · Van Beuningenplein",
    directions: "Go through the gate, cross the courtyard, and go through the doors on the right side of the building. Take the stairs and find us on the first floor (above the gym)."
  },
  {
    name: "VRANKRIJK",
    address: "Spuistraat 216, 1012 VT Amsterdam",
    transport: "Tram 2, 12 · Paleisstraat\nTram 5, 13, 17 · Dam/Raadhuisstraat\nTram 4, 14 · Dam"
  },
  {
    name: "DE RICHEL",
    address: "Nieuwezijds Voorburgwal 282H, 1012 RT Amsterdam",
    transport: "Tram 2, 12 · Paleisstraat\nTram 4, 14 · Dam / Rokin\nMetro 52 · Rokin"
  },
  {
    name: "PROSTITUTION INFORMATION CENTER (PIC)",
    address: "Enge Kerksteeg 3 1012 GV Amsterdam",
    transport: "Tram 4 or 14 · Dam\nTram 2, 12, 13, 17 · Nieuwezijds Kolk"
  },
  {
    name: "THE OTHERSIDE",
    address: "Rigakade 10, 1013 BC Amsterdam"
  },
  {
    name: "DE SERING",
    address: "Rhoneweg 6, 1043 AH Amsterdam"
  }
];
</script>

<template>
  <b-container fluid class="view-background" :style="{ backgroundImage: 'url(' + background + ')' }">
    <b-row class="move-right py-5">
      
<b-col cols="12" class="mb-5">
        <div class="titles1 mb-3">{{ translations[currentLang].accessibilityTitle }}</div>
        <div v-for="link in translations[currentLang].accessibilityLinks" :key="link.text" class="mb-2">
          <a :href="link.url" target="_blank" class="text-dark text-decoration-none">
            <p class="text mb-0"><u>{{ link.text }}</u></p>
          </a>
        </div>
      </b-col>

      <b-col cols="12" class="mb-5">
        <div class="titles1 mb-4">{{ translations[currentLang].ticketsTitle }}</div>
        <p class="text mb-1"><strong>{{ translations[currentLang].ticketsPrice }}</strong></p>
        <p class="text mb-3">{{ translations[currentLang].cineville }}</p>
        
        <p class="text mb-1"><strong>{{ translations[currentLang].workshopsPrice }}</strong></p>
        <p class="text">
          {{ translations[currentLang].presale }} 
          <a href="https://www.amsterdamalternative.nl" target="_blank" class="text-dark"><u>https://www.amsterdamalternative.nl</u></a>
        </p>
        
        <p class="text mt-4 italic-info">{{ translations[currentLang].ticketInfo }}</p>
      </b-col>

<b-col cols="12" class="mb-5">
  <div class="titles1">
    <a :href="translations[currentLang].venueUrl" target="_blank" class="text-dark text-decoration-none">
      <u>{{ translations[currentLang].venueTitle }}</u>
    </a>
    <span class="venue-sub ms-2">— {{ translations[currentLang].venueSub }}</span>
  </div>
  
  <div v-for="venue in venues" :key="venue.name" class="mb-5">
    <div class="venue-name">{{ venue.name }}</div>
    <div class="text">{{ venue.address }}</div>
    
    <div v-if="venue.transport" class="text mt-3 whitespace-pre">
      <strong>Public transport:</strong><br>{{ venue.transport }}
    </div>
    
    <div v-if="venue.directions" class="text mt-3 italic-info">
      {{ venue.directions }}
    </div>
  </div>
</b-col>

      <b-col cols="12" class="mb-5">
        <div class="titles1">{{ translations[currentLang].triggerTitle }}</div>
        <p v-for="(p, i) in translations[currentLang].triggerText" :key="i" class="text mb-3">
          {{ p }}
        </p>
      </b-col>

    </b-row>
  </b-container>
</template>

<style scoped>
.lang-label { font-weight: bold; color: #555; font-family: sans-serif; font-size: 0.9rem; }
.active-lang { color: #000; }

:deep(.form-check-input) {
  cursor: pointer;
  background-color: #6a4da1 !important;
  border-color: #6a4da1 !important;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'%3e%3ccircle r='3' fill='%23fff'/%3e%3c/svg%3e") !important;
}

:deep(.form-check-input:checked) {
  background-color: #6a4da1 !important;
}

.bold { font-weight: bold; }
.titles { font-size: 3em; font-weight: bold; line-height: 1.1; }
.titles1 { font-size: 1.8em; font-weight: bold; margin-top: 2rem; }
.move-right { margin-left: 25px; margin-right: 25px; }
.block { font-weight: 500; font-size: 1.3em; }

@media (max-width: 576px) {
  .titles { font-size: 2em; }
  .text { font-size: 0.9em; }
  .move-right { margin-left: 15px; margin-right: 15px; }
}

.venue-sub { font-weight: normal; font-size: 0.6em; font-style: italic; }
.venue-name { font-size: 1.4em; font-weight: bold; margin-bottom: 0.2rem; margin-top: 1.5rem; }
.whitespace-pre { white-space: pre-line; }
.italic-info { font-style: italic; opacity: 0.9; }
</style>