<template>
<v-toolbar
    dark
    :color="isFrontPage ? 'rgb(0,0,0,0)' : '#006591'"
    fixed
    :app="isFrontPage ? false : true"

    :dense="isFrontPage ? false : false"
    :flat="isFrontPage"
    :scroll-off-screen="isFrontPage"
    :prominent="isFrontPage"
    :scroll-threshold="isFrontPage ? 150 : undefined"

    >
      <v-btn
        nuxt
        to="/"
        flat
      >
        Home
        </v-btn>
      <v-btn
        nuxt
        to="/about"
        flat
      >
        About
      </v-btn>
      <v-btn
      nuxt
      to="/projects"
      flat
      >
        Projects
      </v-btn>
      <v-spacer />
      <v-btn
      color="#57B4D6"
      >
        Contact
      </v-btn>
    </v-toolbar>
</template>

<script>
  export default {
    props: {
      isFrontPage: Boolean
    }
  }
</script>
