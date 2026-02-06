<script setup lang="ts">
import { BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref } from 'vue';

const background = new URL('../assets/sponsor_background.png', import.meta.url).href
const cultuurfonds = new URL('../assets/cultuurfonds.png', import.meta.url).href
const afk = new URL('../assets/afk.png', import.meta.url).href
const sponsors = new URL('../assets/sponsors.png', import.meta.url).href

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
 <b-row class="mt-5 justify-content-center">
      <b-col xs="11" lg="7" class="mt-5 text-center text-container">
        <h1 class="sponsor-title">
          The incredible sponsors that help bring the festival to life
        </h1>
        
        <p class="description-text mt-4">
          As Porn Film Festival Amsterdam grows, partnerships that reflect our values of community, plurality, art and pleasure become more essential.
        </p>
        
        <p class="description-text mt-3">
          The following companies and funds have helped make the festival more sustainable and continued to offer their support, energy and expertise.
        </p>
      </b-col>
    </b-row>

    <b-row class="justify-content-center">
      <b-col lg="10" class="my-5">
        <a target="_blank" rel="noopener noreferrer" href="https://f2f.com/">
          <img :src="sponsors" class="img-fluid" />
        </a>
      </b-col>
    </b-row>

<b-row class="justify-content-center">
  <b-col lg="6" class="mt-5 d-flex justify-content-center align-items-center">
    <div class="text-center black-box mb-5">
      FUNDS
    </div>
  </b-col>
</b-row>

<b-row class="justify-content-center">
  <b-col lg="8" class="mt-4 mb-2 text-center">
    <p class="attribution-text">
      Dit project is (mede) mogelijk gemaakt met financiële steun van Fonds 21.
    </p>
  </b-col>
</b-row>

<b-row class="justify-content-center">
  <b-col lg="8" class="mb-5 d-flex justify-content-center align-items-center gap-4">
    <a target="_blank" rel="noopener noreferrer">
      <img :src="afk" class="img-fluid fund-logo" />
    </a>
    <a target="_blank" rel="noopener noreferrer">
      <img :src="cultuurfonds" class="img-fluid fund-logo" />
    </a>
  </b-col>
</b-row>

  </b-container>
</template>

<style scoped>

.black-box {
  background-color: black;
  color: white;
  padding: 10px;
  width: 100%; /* Narrower width */
  height: 50%; /* Taller height */
}


@media (max-width: 576px) {
  .sponsor-text {
    font-size: 1.2em; /* Reduce text size on smaller screens */
  }
}

.text-container {
  color: #000; /* Adjust color based on your background contrast */
}

.sponsor-title {
  font-size: 2.8rem;
  font-weight: 800; /* Extra bold for the main header */
  line-height: 1.1;
  margin-bottom: 1.5rem;
}

.description-text {
  font-size: 1.25rem;
  font-weight: 500; /* Medium weight to match the screenshot */
  line-height: 1.4;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

/* Mobile Adjustments */
@media (max-width: 768px) {
  .sponsor-title {
    font-size: 1.8rem;
  }
  .description-text {
    font-size: 1.1rem;
  }
}

/* Maintain your existing box styles */
.black-box {
  background-color: black;
  color: white;
  padding: 10px 30px;
  display: inline-block;
}
</style>
