
<template>
<div width="100%" >
  <PageTitle upperCase titleText="About me"></PageTitle>

  <v-timeline>
    <v-timeline-item
      v-for="(year, i) in years"
      :key="i"
      :color="year.color"
      fill-dot
    >

      <template v-slot:opposite>
        <span
          :class="`headline font-weight-bold ${year.color.substr(0,year.color.indexOf(' '))}--text`"
          dark
          v-text="$t(year.year)"
        ></span>
      </template>
      <v-card
        :color="year.color"
        dark
      >
       <v-card-title class="title" v-text="$t(year.title)"></v-card-title>
       <v-card-text class="white text--primary">
          <p v-text="$t(year.shortDescription)"></p>
          <v-btn
            v-if="year.readMore"
            :color="year.color"
            class="mx-0"
            outline
          >
            {{ $t('common.read-more') }}
          </v-btn>
        </v-card-text>
      </v-card
      >
    </v-timeline-item>
  </v-timeline>
  </div>
</template>

<script>

import PageTitle from '~/components/PageTitle.vue'

export default {
  components: {
    PageTitle
  },
    data: () => ({
      years: [
        {
          color: "orange darken-2",
          year: "resume.dfind.period",
          title: "resume.dfind.title",
          shortDescription: 'resume.dfind.description',
          readMore: "yes",
        },
        {
          color: 'blue darken-1',
          year: 'resume.buypass.period',
          title: "resume.buypass.title",
          shortDescription:
          `resume.buypass.description`
        },
        {
          color: 'green darken-1',
          year: 'resume.solo-game-dev.period',
          title: "resume.solo-game-dev.title",
          shortDescription: "resume.solo-game-dev.description"
        },
        {
          color: 'cyan lighten-1',
          year: 'resume.master-graduation.period',
          title: "resume.master-graduation.title",
          shortDescription: "resume.master-graduation.description"
        },
        {
          color: "red lighten-1",
          year: 'resume.master-thesis.period',
          title: "resume.master-thesis.title",
          shortDescription: "resume.master-thesis.description"
        },
        {
          color: 'teal lighten-1',
          year: 'resume.embassy.period',
          title: "resume.embassy.title",
          shortDescription: "resume.embassy.description"
        },
        {
          color: 'grey darken-1',
          year: 'resume.oslo-university.period',
          title: "resume.oslo-university.title",
          shortDescription: "resume.oslo-university.description"
        },
        {
          color: 'orange lighten-2',
          year: 'resume.kwansei-gakuin.period',
          title: "resume.kwansei-gakuin.title",
          shortDescription: "resume.kwansei-gakuin.description"
        }
      ]
    })
  }
</script>