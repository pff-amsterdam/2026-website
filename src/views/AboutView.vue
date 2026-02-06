<script setup lang="ts">
import { BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref } from 'vue';

const background = new URL('../assets/about_background.png', import.meta.url).href

// 1. Language State
const currentLang = ref<'en' | 'nl'>('en');

const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

// 2. All Translated Content
const translations = {
  en: {
    mainTitle: "About Us",
    intro1: "Porn Film Festival Amsterdam was created to fill a striking gap. For a city internationally known for its Red Light District, sexual freedom and LGBTQIA+ vibrancy, Amsterdam had no annual film festival dedicated to sex, gender and sexuality in a broad sense until 2024. PFFA stepped into that space with a simple but radical belief: <strong>Porn doesn’t have to be disposable. It can be artistic, political, moving, thought-provoking and a catalyst for self-discovery.</strong>",
    intro2: "Unlike festivals focused on a single identity, Porn Film Festival Amsterdam doesn’t narrow itself to one community. Instead, we aim to widen and to connect, creating a space where many experiences of sexuality can coexist, be seen and be discussed.",
    principlesTitle: "Our guiding principles",
    curationTitle: "How we curate Porn Film Festival Amsterdam",
    curationText: [
      "Porn Film Festival Amsterdam rejects classic porn categories. We do not curate porn based on the physical appearance of actions of the performers, we curate based on the content and message. We treat porn as cinema. We do not aim to please and to narrow expectations. Instead, our curatorial approach brings together films that offer different perspectives on sex and sexuality. Some pieces confront. Some delight. Some provoke. Some seduce. Some unsettle.",
      "What matters is the content and the meaning, not the category.",
      "By doing so, we situate porn within a meaningful artistic context and recognise filmmakers and performers as cultural producers with something to say, not just bodies on screen.",
      "Because sex, porn and sex work still carry heavy taboos, those who create erotic films often face censorship and misconceptions. Porn Film Festival Amsterdam offers a rare platform where their work can be seen, discussed, celebrated and brought to a wider public.",
      "Q&As, workshops, performances, installations, debates and community events invite visitors to explore further, engage critically and build connections across experiences and identities.",
      "Read <strong><u>more</u></strong> on how we make space for the independent curation while maintaining core Porn Film Festival Amsterdam intentions."
    ],
    receptionTitle: "Critical Reception",
    historyTitle: "Who are we and how did we get here?",
    historyText1: "We are a group of debauchees, cinephiles, activists, filmmakers, media scholars and sex workers. Most of us met some years ago at Filmhuis Cavia in Amsterdam, a community-run cinema founded by the squatters’ movement of the 80s.",
    historyText2: "In 2024, our festival came to life with the tremendous support of the local and global porn community, as well as the trust of local funds, grassroots venues and lots of friends and allies.",
    teamTitle: "Who Are We Really?"
  },
  nl: {
    mainTitle: "Over ons",
    intro1: "Porn Film Festival Amsterdam werd opgericht vanuit de eenvoudige maar radicale overtuiging dat <strong>porno geen wegwerpartikel is. Als kunstzinnig en politiek filmgenre kan het ontroeren, tot denken aanzetten en is het een katalysator voor zelfontdekking.</strong> In een stad als Amsterdam die wereldwijd bekend staat om haar Wallen en seksuele vrijheid, misten we een jaarlijks terugkerend festival waar seks, gender en seksualiteit in brede zin konden worden gevierd en besproken.",
    intro2: "In 2024 besloten we om in dat gat te springen met een festival dat zich niet richt op één identiteit of gemeenschap, maar er juist naar streeft om te verbreden en te verbinden. Porn Film Festival Amsterdam wil een ruimte zijn voor uitwisseling en nieuwsgierigheid naar de ander. Een plek waar verschillende belevingen van seksualiteit samenkomen, gezien mogen worden en elkaar kunnen inspireren en uitdagen.",
    principlesTitle: "Onze peilers",
    curationTitle: "Hoe we porno programmeren",
    curationText: [
      "Porn Film Festival Amsterdam wijst klassieke pornocategorieën af. We selecteren porno niet op basis van het uiterlijk of de handelingen van de acteurs, maar behandelen haar als cinema. We kijken naar thematiek en kwaliteit. Met deze aanpak brengen we films bij elkaar die samen een ander licht werpen op seks en seksualiteit. Sommige films zullen confronteren, andere plezieren. Sommige films provoceren, weer andere verleiden. Sommige brengen je van je stuk.",
      "Het is ons te doen om de inhoud, niet om de categorie.",
      "Deze manier van cureren plaatst porno in een betekenisvolle artistieke context en erkent filmmakers en performers als inhoudelijke cultuurmakers.",
      "Omdat er helaas nog altijd zware taboes rusten op seks, porno en sekswerk, krijgen ook erotische filmmakers te maken met censuur en vooroordelen, waardoor het moeilijk kan zijn om een publiek te bereiken.",
      "Met een randprogramma van workshops, performances, installaties, publieke gesprekken en sekspositieve feesten nodigen we bezoekers uit om op onderzoek uit te gaan, zich te laten verrassen door andere perspectieven en ook buiten hun hokjes verbinding aan te gaan.",
      "Lees <strong><u>meer</u></strong> over de persoonlijke werkwijzen van onze zeven programmeurs en hun gemeenschappelijke doelstellingen."
    ],
    receptionTitle: "Kritische ontvangst",
    historyTitle: "Wie zijn we en hoe zijn we hier beland?",
    historyText1: "We zijn een groep losbollen, cinefielen, activisten, filmmakers, academici en sekswerkers. De meesten van ons ontmoetten elkaar jaren geleden in Filmhuis Cavia in Amsterdam. Een kleine bioscoop die in de jaren 80 werd opgericht vanuit de kraakbeweging.",
    historyText2: "Het Porn Film Festival Amsterdam kwam in 2024 tot leven met de immense steun van lokale en globale pornogemeenschap en het vertrouwen van lokale fondsen, alternatieve plekken en een heleboel vrienden en bondgenoten.",
    teamTitle: "Wie zijn we echt?"
  }
};

const principles = [
  {
    title: { en: 'Plurality.', nl: 'Meerstemmigheid' },
    description: {
      en: 'Many have been made invisible by the leading culture. Many others have been objectified by it. Here they take the lead and bring their own desires and legacy to the fore.',
      nl: 'Vele stemmen blijven ongehoord in de mainstream cultuur. Vele andere worden erdoor geobjectiveerd. Hier voeren ze de boventoon en laten hun eigen verlangens en verhalen helder klinken.'
    }
  },
  {
    title: { en: 'Art.', nl: 'Kunst' },
    description: {
      en: 'Porn is a film genre and as such it demands artistic value. Cinema illuminates, expands and defies reality with its endless stream of perceptions.',
      nl: 'Als filmgenre verdient porno professionele erkenning en (kunst)kritiek. Cinema verheldert, verruimt en daagt de werkelijkheid uit met haar eindeloze stroom aan perspectieven.'
    }
  },
  {
    title: { en: 'Pleasure.', nl: 'Genot' },
    description: {
      en: 'Porn enriches our sex life and helps us explore fantasies. Desire is extremely layered and ambiguous and we need others to know ourselves better.',
      nl: 'Porno verrijkt ons seksleven en helpt ons om onze fantasieën te verkennen. Omdat verlangen al eeuwen onderhevig is aan taboes, is het gelaagd en ambigu.'
    }
  },
  {
    title: { en: 'Community.', nl: 'Gemeenschap' },
    description: {
      en: 'We live in a city which, while calling itself tolerant, makes it increasingly hard for many to feel welcome. We believe in the potential of real-life encounters.',
      nl: 'We geloven in de kracht van ontmoetingen (in levende lijve) om de publieke ruimte te heroveren als plek voor iedereen. Porno kijken in de bioscoop is anders dan thuis.'
    }
  }
];

const teamMembers = [
  {
    name: 'Bear Silver (He/They)',
    description: {
      en: 'is an activist and performer who has been involved in various grassroots initiatives in Amsterdam since 1999. Since 2016, Bear has been involved in ethical pornography.',
      nl: 'is een activist en performer die sinds 1999 betrokken is bij verschillende grassroots-initiatieven in Amsterdam. Sinds 2016 maakt Bear ook ethische pornografie.'
    }
  },
  {
    name: 'Erik ter Veld (He/Him)',
    description: {
      en: 'is a filmmaker from Groningen whose work focuses on the challenges of body and mind, and resilience and passion in the face of adversity.',
      nl: 'is een filmmaker uit Groningen die zich in zijn werk richt op mentale en fysieke uitdagingen en het tonen van veerkracht en passie bij tegenslagen.'
    }
  },
  {
    name: 'Franka Bauwens (She/They)',
    description: {
      en: 'loved hanging around at Filmhuis Cavia during her studies in philosophy. She currently works at a grassroots publishing company for theatre, teaches and translates.',
      nl: 'hing tijdens haar studie filosofie graag rond in Filmhuis Cavia. Nu vertaalt ze, geeft ze les en werkt ze voor een toneeluitgeverij.'
    }
  },
  {
    name: 'hyeisoos (She/Her)',
    description: {
      en: 'is an artist from South Korea living in the Netherlands. She currently follows a Research Master in Cultural Analysis at the University of Amsterdam.',
      nl: 'woont als Zuid-Koreaanse kunstenaar in Nederland. Ze volgt momenteel de onderzoeksmaster Culturele Analyse aan de UvA.'
    }
  },
  {
    name: 'Jessica van der Berg (She/Her)',
    description: {
      en: 'is from Johannesburg, South Africa. As a copywriter and recent graduate of Sextech School, she has given lectures on masturbation, vulvas and ethical pornography.',
      nl: 'komt uit Johannesburg, Zuid-Afrika. Als copywriter en alumnus van de Sextech School gaf ze lezingen over masturbatie, vulvas en ethische pornografie.'
    }
  },
  {
    name: 'Luisa González (She/They)',
    description: {
      en: 'is a film programmer with over fourteen years of experience. She is Colombian and lives in Amsterdam. Currently, she is completing her PhD research.',
      nl: 'is een filmprogrammeur met meer dan veertien jaar ervaring. Ze is Colombiaanse en woont in Amsterdam. Momenteel werkt ze bij de UvA aan haar PhD-onderzoek.'
    }
  },
  {
    name: 'Samuel Witteveen Gómez (He/They)',
    description: {
      en: 'has been part of the programming team at Filmhuis Cavia for over seven years. He is a writer and journalist and currently works as researcher at VPRO/HUMAN.',
      nl: 'was zeven jaar lang deel van het programmateam van Filmhuis Cavia. Hij is schrijver en journalist en werkt momenteel als onderzoeker bij VPRO/HUMAN.'
    }
  }
];

const pressQuotes = [
  {
    name: 'Le Monde (full report): ',
    description: 'A Amsterdam, voyage au pays du porno alternatif',
    link: 'https://www.lemonde.fr/m-le-mag/article/2022/04/22/a-amsterdam-voyage-au-pays-du-porno-alternatif_6123281_4500055.html'
  },
  {
    name: 'NRC: ',
    description: 'Perverse pracht en seksvampiers: het eerste Amsterdamse pornofestival wil de kijker uitdagen, laten schrikken, veranderen',
    link: 'https://www.nrc.nl/nieuws/2022/04/13/perverse-pracht-en-seksvampiers-het-eerste-amsterdamse-pornofestival-wil-de-kijker-uitdagen-laten-schrikken-veranderen-a4112678'
  },
  {
    name: 'Het Parool: ',
    description: 'Spannend, geil en soms misschien een beetje ongemakkelijk: Amsterdam heeft nu ook een Porn Film Festival',
    link: 'https://www.parool.nl/amsterdam/spannend-geil-en-soms-misschien-een-beetje-ongemakkelijk-amsterdam-heeft-nu-ook-een-porn-film-festival~b09a13a7/'
  }
];
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
    
    <b-row class="mt-5 move-right">
      
      <b-col cols="12" class="mt-5 mb-2">
        <div class="d-flex align-items-center">
          <span class="lang-label me-2" :class="{ 'active-lang': currentLang === 'nl' }">NL</span>
          <b-form-checkbox 
            :model-value="currentLang === 'en'" 
            @change="toggleLang" 
            switch 
            size="lg"
            class="custom-switch"
          />
          <span class="lang-label ms-2" :class="{ 'active-lang': currentLang === 'en' }">ENG</span>
        </div>
      </b-col>

      <b-col cols="12">
        <div class="titles">{{ translations[currentLang].mainTitle }}</div>
        
        <p class="text mt-3" v-html="translations[currentLang].intro1"></p>
        <p class="text">{{ translations[currentLang].intro2 }}</p>
      </b-col>

      <b-col cols="12">
        <div class="titles1 mb-4">{{ translations[currentLang].principlesTitle }}</div>
        <b-row class="four-blocks mb-4">
          <b-col v-for="(principle, index) in principles" :key="index" cols="12" md="3">
            <div class="block"><strong>{{ principle.title[currentLang] }}</strong></div>
            <p class="text">{{ principle.description[currentLang] }}</p>
          </b-col>
        </b-row>
      </b-col>

      <b-col cols="12">
        <div class="titles1 mb-4">{{ translations[currentLang].curationTitle }}</div>
        <p v-for="(p, i) in translations[currentLang].curationText" :key="i" class="text" v-html="p"></p>
      </b-col>

      <b-col cols="12">
        <div class="titles1 mb-4">{{ translations[currentLang].receptionTitle }}</div>
        <div v-for="(quote, index) in pressQuotes" :key="index" class="mb-3">
          <p class="text">
            <strong>{{ quote.name }}</strong>
            <a :href="quote.link" target="_blank" class="text-dark ml-1"><u>{{ quote.description }}</u></a>
          </p>
        </div>
      </b-col>

      <b-col cols="12">
        <div class="titles1 mb-4">{{ translations[currentLang].historyTitle }}</div>
        <p class="text">{{ translations[currentLang].historyText1 }}</p>
        <p class="text">{{ translations[currentLang].historyText2 }}</p>
      </b-col>

      <b-col cols="12">
        <div class="titles1 mb-4">{{ translations[currentLang].teamTitle }}</div>
        <div v-for="(member, index) in teamMembers" :key="index" class="mb-4">
          <p class="text">
            <span class="bold">{{ member.name }}</span> {{ member.description[currentLang] }}
          </p>
        </div>
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
</style>