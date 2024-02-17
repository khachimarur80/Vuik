<template>
  <vk-navbar/>
  <vkHero/>
  <vkServices/>
</template>

<script>
import vkNavbar from './components/navbar/vk-navbar-2.vue'
import vkHero from './components/hero/vk-hero-1.vue'
import vkServices from './components/services/vk-services-1.vue'

export default {
  name: 'App',
  components: {
    vkNavbar,
    vkHero,
    vkServices,
  },
  data: () => ({
    theme: {
      primary: '#2196F3',
      secondary: '#1976D2',
      accent: '#FFC107',
      error: '#f44336',
      warning: '#FF9800',
      info: '#03A9F4',
      success: '#4CAF50',
      text: '#333',
      text_secondary: '#666',
      text_light: '#eee',
      text_dark: '#111',
      background: '#f9f9f9',
      background_dark: '#888',
      background_light: '#ffffff',
      text_font: 'HelveticaNeue-Thin',
      title_font: 'HelveticaNeue',
    }
  }),
  mounted() {
    for (let key in this.theme) {
      document.documentElement.style.setProperty('--vk-'+key.replace('_', '-'), this.theme[key])
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
html, body {
  margin: 0px;
  padding: 0px;
}
</style>
