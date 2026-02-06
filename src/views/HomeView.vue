<script setup lang="ts">
const open_call = new URL('../assets/2026OpenCall.png', import.meta.url).href;
import { BContainer, BRow, BCol, BButton, BImg } from 'bootstrap-vue-3';
const pffaLogo = new URL('../assets/pffa_logo.png', import.meta.url).href
const footerlogo = new URL('../assets/footer.png', import.meta.url).href
const dates = new URL('../assets/2026_dates.png', import.meta.url).href
const full_timetable = new URL('../assets/full_timetable.png', import.meta.url).href
const background = new URL('../assets/background.png', import.meta.url).href
</script>

<template>
  <b-container 
    fluid 
    class="d-flex flex-column min-vh-100 px-0 **view-background**"
    :style="{ backgroundImage: 'url(' + background + ')' }" 
  >
  <b-row>
<b-col xs="12" lg="6" class="mt-5">
  <b-row class="mt-5 px-3"> 
    <b-img :src="pffaLogo" fluid></b-img>
  </b-row>

  <b-row class="mt-3">
    <b-col lg="8" style="padding-left: 50px;">
      <a href="https://drive.google.com/file/d/1H1VmGxGCWJ7dFVx-Ivuw8MibUtWI2VGE/view?usp=sharing" target="_blank">
        <b-img :src="full_timetable" fluid></b-img>
      </a>
    </b-col>
  </b-row>

</b-col>
<b-col xs="12" lg="4" class="mt-5">
  <b-row>
    <b-img fluid :src="dates" class="dates-desktop-spacer"></b-img>
  </b-row>
</b-col>

  </b-row>
  <b-img :src="footerlogo"  class="footer-image" fluid></b-img>
</b-container>

</template>

<style scoped>

/* 1. Mobile First: Keep it simple for phones */
.dates-desktop-spacer {
  margin-top: rem;
  padding: 0 10%; /* Keeps it from hitting phone edges */
}

/* 2. Desktop: Apply the "Big Gap" only on large screens */
@media (min-width: 992px) {
  .dates-desktop-spacer {
    margin-top: 30vh !important; /* Pushes it down to the sweet spot */
    padding: 0;
  }
}

.view-background {
  background-size: cover;          /* Ensures the image covers the entire element */
  background-position: center center; /* Centers the image */
  background-repeat: no-repeat;    /* Prevents tiling */
  background-attachment: scroll;
  
}

.custom-button-width {
  width: 350px; /* Adjust this value as needed for your desired fixed width */
}

.custom-button-width {
  width: 350px; /* Adjust this value as needed for your desired fixed width */
}

/* Footer styles */
.footer-image {
  width: 100%;
  margin-top: auto;
  margin-bottom: 0px;
}

.form-button {
  background-color: #D9D9D9 !important;
  border-color: #D9D9D9 !important;
  color: black !important;
  font-weight: bold !important;
}
</style>