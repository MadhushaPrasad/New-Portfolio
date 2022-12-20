<template>
  <v-layout column justify-center align-center class="mt-4 pt-2">
    <VueCompareImage
      class="hidden-md-and-down"
      hover
      :style="{ minWidth: '1300px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage"
      :rightImage="rightImage"
      :sliderPositionPercentage="sliderPosition"
    />
    <VueCompareImage
      class="hidden-lg-and-up"
      hover
      :style="{ maxWidth: '400px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage2"
      :rightImage="rightImage2"
      :sliderPositionPercentage="sliderPosition"
    />

    <br />

    <vue-typer class="headline" :repeat="0" text="Madhusha Prasad"></vue-typer>
    <vue-typer
      :text="text1"
      :repeat="Infinity"
      :shuffle="false"
      initial-action="erasing"
      :pre-type-delay="70"
      :type-delay="70"
      :pre-erase-delay="1980"
      :erase-delay="150"
      erase-style="select-back"
      :erase-on-complete="false"
      caret-animation="smooth"
    ></vue-typer>
    <br />
    <v-flex xs12 sm6 md4 lg4 xl4>
      <v-card flat color="transparent" max-width="500">
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-10">
              <span>About</span>
              <span class="green--text"> Me</span>
            </h3>
            <div>
              <p>
                Hello! I’m Madhusha Prasad. am 23 years old. And I am
                <span class="blue--text font-weight-bold"
                  >FOSS Enthusiast, Blogger, Currently reading BSc (Hons) Degree
                  in IT specializing in Software Engineering at Srilanka
                  Institute Of Information Technology (SLIIT).</span
                >
                My fields of interest are
                <span class="green--text font-weight-bold"
                  >web development, UI/UX designing, mobile application
                  development.</span
                >
                I have two internships as of Trainee Associate Software Engineer
                in Sentura technologies and NeoMinds companies.
                <span class="green--text font-weight-bold">
                  I have special interests in volunteering in Open Source
                  Communities and writing articles for Blogspot, Medium.</span
                >
              </p>
            </div>
          </div>
        </v-card-title>

        <v-card-actions class="hidden-sm-and-down">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            fab
            dark
            outline
            color="green"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{ icon.icon }}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-card-actions class="hidden-md-and-up justify-center">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            small
            fab
            dark
            outline
            color="green"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{ icon.icon }}</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import { VueTyper } from 'vue-typer'
import VueCompareImage from 'vue-compare-image'

export default {
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
      { property: 'og:url', content: 'https://eldin.space' },
      {
        property: 'og:image',
        content: 'https://i.imgur.com/Dcz2PGx.jpg'
      },
      { property: 'og:description', content: "Madhusha Prasad's Portfolio" }
    ]
  },
  components: {
    'vue-typer': VueTyper,
    VueCompareImage
  },
  data () {
    return {
      icons: [
        { href: 'https://github.com/EldinZaimovic', icon: 'fab fa-github' },
        {
          href: 'https://stackoverflow.com/users/story/9660700',
          icon: 'fab fa-stack-overflow'
        },
        { href: 'https://twitter.com/EldinMatricar', icon: 'fab fa-twitter' },
        {
          href: 'https://www.linkedin.com/in/eldin-zaimovic',
          icon: 'fab fa-linkedin-in'
        },
        {
          href: 'https://www.facebook.com/EldinVasVoli',
          icon: 'fab fa-facebook-f'
        },
        { href: 'https://www.instagram.com/matricar', icon: 'fab fa-instagram' }
      ],
      text1: ['Front-End Developer', 'Web Developer', 'Web Designer'],
      leftImage: 'https://i.imgur.com/bU50uS9.jpg',
      rightImage: 'https://i.imgur.com/z3ZoEEw.jpg',
      leftImage2: 'https://i.imgur.com/SXBitjh.jpg',
      rightImage2: 'https://i.imgur.com/Dcz2PGx.jpg',
      sliderLine: 0,
      hSize: 0,
      sliderPosition: 0.5
    }
  }
}
</script>
<style>
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }

  50% {
    transform: rotateZ(10deg);
  }
}

.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
  color: green;
}
.vue-typer .custom.char.selected {
  color: #e91e63;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: green;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #e91e63;
}
</style>
