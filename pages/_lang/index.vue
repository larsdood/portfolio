<template>
<div width="100%" >
    <v-parallax height="700" src="/images/fuji.jpeg">
      <img class="title" src="/name-title.png">
      <img :class="$t('images.subtitleClass')" :src="$t('images.subtitle')">
    </v-parallax>

<br/>
<br/>
   <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <v-card>
        <v-card-title class="headline">Web developer from Norway</v-card-title>
        <v-card-text>
          <p>Greetings.</p>

          <p>My name is Lars Holdaas and I'm a Norwegian web developer.</p>

          <p>I'm currently making this site using Vue with Nuxt/Vuetify as a personal study project.</p>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn
            nuxt
            to="/about"
          >About</v-btn>
          <v-btn 
            nuxt color="rgb(0, 101, 145)" dark to="/projects/" >
            Projects
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
  <br/>
  <br/>
  <br/>

    </div>
</template>

<style>
.title{
    width:100%;
    max-width:445px;
    margin: 1em auto 1em;
}
.subtitle-en{
  width: 100%;
  max-width: 416px;
  margin: 0 auto 1em;
}
.subtitle-jp{
  width: 100%;
  max-width: 670px;
  margin: 0 auto 1em;
}
</style>

<script>
export default {
  layout: "frontpage"
}
</script>