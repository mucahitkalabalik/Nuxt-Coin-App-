<template>
  <v-app>
    <app-header/>
    <nuxt/>
    <app-footer/>
   
  </v-app>
</template>

<script>
import AppFooter from '../components/AppFooter.vue'
import AppHeader from '../components/AppHeader.vue'
export default {
components:{AppHeader, AppFooter}
}
</script>

<style>

</style>