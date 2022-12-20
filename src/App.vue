<template>
  <v-app :dark="goDark">
    <v-content>
      <v-container align-center>
        <TheHeader :goDark="goDark" @changeTheme="updateTheme($event)" />

        <transition
          name="router-animation"
          mode="out-in"
          enter-active-class="animated fadeIn fast"
          leave-active-class="animated fadeOut faster"
        >
          <router-view></router-view>
        </transition>
      </v-container>
    </v-content>
    <TheFooter />
  </v-app>
</template>

<script>
import TheHeader from './components/TheHeader'
import TheFooter from './components/TheFooter'

export default {
  name: 'App',
  metaInfo: {
    title: 'Home',
    titleTemplate: "%s ← Madhusha Prasad's Space",
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { name: 'description', content: "Madhusha Prasad's Portfolio" },
      { charset: 'utf-8' },
      { property: 'og:title', content: 'Madhusha Prasad' },
      { property: 'og:site_name', content: 'Madhusha Prasad' },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://github.com/MadhushaPrasad' },
      {
        property: 'og:image',
        content: 'https://user-images.githubusercontent.com/50085447/208628744-ead18481-11c2-46be-abea-68817a2b3ce7.jpg'
      },
      { property: 'og:description', content: "Madhusha Prasad's Portfolio" }
    ]
  },
  components: {
    TheHeader,
    TheFooter
  },
  data () {
    return { goDark: false }
  },
  methods: {
    updateTheme (updatedTheme) {
      this.goDark = !updatedTheme
    }
  }
}
</script>
<style>
@import "https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.0/animate.min.css";
</style>
