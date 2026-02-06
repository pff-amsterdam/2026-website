<script setup lang="ts">
import { BImg, BRow, BCol } from 'bootstrap-vue-3';

// Added 'reverse' to props
const props = defineProps(['image', 'title', 'time', 'place', 'description', 'duration', 'text', 'imagelogo', 'ticket', 'reverse', 'isFirst']);
</script>

<template>
  <b-row class="mb-5 no-gutters align-items-center">
    <b-col 
      xs="12" 
      lg="4" 
      :offset-lg="props.reverse ? 0 : 1" 
      :order-lg="props.reverse ? 2 : 1"
    > 
      <div class="media-stack" :class="{ 'ms-lg-auto': props.reverse }">
        <b-img :src="props.image" class="standard-image" />

        <div class="action-bar">
          <a :href="props.ticket" target="_blank" rel="noopener noreferrer" style="text-decoration: none;">
        <button v-if="props.ticket" class="buy-button">
          {{ props.text === props.text?.nl || props.duration?.includes('Totale') ? 'kaartjes' : 'Buy ticket' }}
        </button>
          </a>
          <img :src="props.imagelogo" alt="Venue Logo" class="venue-logo">
        </div>
      </div>
    </b-col>

    <b-col 
      xs="12" 
      lg="5" 
      :offset-lg="props.reverse ? 1 : 0"
      :order-lg="props.reverse ? 1 : 2"
      :class="[props.reverse ? 'text-column-adjustment-reverse' : 'text-column-adjustment']"
    > 
      <h2 class="title-text" v-html="props.title"></h2>
      <h3 class="subtitle-text">{{ props.time }} | {{ props.place }}</h3>
        
        <div class="content-text mt-3" v-html="props.text"></div>
        <div class="content-text mt-3" v-html="props.description"></div>
      
    <p v-if="props.duration" class="mt-2" v-html="props.duration"></p>
    </b-col>
    
    <b-col cols="12" v-if="!props.isFirst">
      <hr class="section-divider"/>
    </b-col>
  </b-row>
</template>

<style scoped>

.standard-image {
  width: 100%;
  height: auto;
  display: block;
}

.media-stack {
  display: flex;
  flex-direction: column;
  max-width: 380px;
}

.action-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin-top: 15px;
}

.buy-button {
  background-color: #2C2C2C;
  color: white;
  border: none;
  padding: 10px 24px;
  cursor: pointer;
  border-radius: 8px;
  font-weight: bold;
  transition: opacity 0.2s;
}

.venue-logo {
  height: 45px;
  width: auto;
}

.section-divider {
  border-top: 3px solid #000000;
  width: 80%;
  margin: 40px auto;
  opacity: 1;
}

@media (min-width: 992px) {
  /* Standard: Pull text left toward image */
  .text-column-adjustment {
    margin-left: -40px; 
    padding-left: 0;
  }
  
  /* Reversed: Pull text right toward image */
  .text-column-adjustment-reverse {
    margin-right: -40px;
    padding-right: 0;
    text-align: right; /* Optional: adjust alignment if it looks better */
  }

  /* Ensures the media stack sticks to the right side of its col when reversed */
  .ms-lg-auto {
    margin-left: auto;
  }
}

@media (max-width: 991px) {
  .media-stack {
    margin-bottom: 2rem;
    max-width: 100%;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>