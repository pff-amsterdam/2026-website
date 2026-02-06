<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink } from 'vue-router'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import type { BCollapse } from 'bootstrap-vue-3'

const icon = new URL('../assets/icon.png', import.meta.url).href

const collapseNavbar = () => {
  const element = document.getElementById('nav-collapse')
  if (element) {
    element.classList.remove('show')
  }
}
</script>

<template>
  <b-navbar toggleable="lg" fixed="top" sticky="true">
    <b-navbar-brand><router-link to="/"><b-img class="logo" fluid :src="icon"/></router-link></b-navbar-brand>
    <b-navbar-toggle target="nav-collapse">
      <font-awesome-icon icon="fa-bars" class="menu"/>
    </b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="nav nav-collapse ml-auto">
                <b-nav-item class="nav-item-spacing"><router-link to="about_us" @click="collapseNavbar">About Us</router-link></b-nav-item>
        <b-nav-item-dropdown>
          <template #button-content>
      Program
      <span class="caret ms-1"></span>
    </template>
        <b-dropdown-item><router-link to="thursday" @click="collapseNavbar">Thur, 26 Feb</router-link></b-dropdown-item>
        <b-dropdown-item><router-link to="I&C" @click="collapseNavbar">Fri, 27 Feb I&C Day</router-link></b-dropdown-item>
        <b-dropdown-item><router-link to="friday" @click="collapseNavbar">Fri, 27 Feb</router-link></b-dropdown-item>
        <b-dropdown-item><router-link to="saturday" @click="collapseNavbar">Sat, 28 Feb</router-link></b-dropdown-item>
        <b-dropdown-item><router-link to="sunday" @click="collapseNavbar">Sun, 1 Mar</router-link></b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item class="nav-item-spacing"><router-link to="info" @click="collapseNavbar">Extra info</router-link></b-nav-item>
        <b-nav-item class="nav-item-spacing"><router-link to="sponsors" @click="collapseNavbar">Sponsors</router-link></b-nav-item>

        <b-nav-item-dropdown>
        <template #button-content>
        Prev. Editions
        <span class="caret ms-1"></span>
        </template>
        <b-dropdown-item class="nav-item-spacing"><a href="https://2024.pornfilmfestival.amsterdam" target="_blank" rel="noopener noreferrer" @click="collapseNavbar">2024</a></b-dropdown-item>
        <b-dropdown-item class="nav-item-spacing"><a href="https://2025.pornfilmfestival.amsterdam" target="_blank" rel="noopener noreferrer" @click="collapseNavbar">2025</a></b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<style scoped>

.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 4px;
  vertical-align: middle;
  border-top: 4px solid;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}

.btn-content::after {
 display: none;
}

.ic {
  color: white;
}
.navbar {
  background-color: black;
}

.nav {
  margin-left: auto;
}

a {
    color: var(--vt-c-white);
    text-decoration: none;
}

.menu {
      color: white;
   }

.nav-link:hover, .nav-link:focus {
    color: white;
}

.show {
  color: white;
}

a:hover {
  color: white;
  text-decoration: underline;
}

.logo {
  max-height: 70px;
}


@media (max-width: 932px) {
   .logo {
     width: 250px;
   }

  .navbar {
    background-color: black;
  }
}

@media (min-width: 932px) {
  .navbar {
    background-color: black;
    max-height: 60px;
  }
}
</style>
