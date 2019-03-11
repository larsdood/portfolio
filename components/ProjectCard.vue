<template>
  <v-card hover class="project-card" :key="project.title">
        <v-card-title v-if="!project.logo || !project.logo.isTitle" class="headline">{{project.title}}</v-card-title>
        <v-card-text>
          <v-img v-if="project.logo" :src="project.logo.url" contain position="left" max-height="5em" max-width="20em"/>
          <br v-if="project.logo" />
          <v-subheader v-if="project.start && project.end" >{{project.start}} - {{project.end}}</v-subheader>
          <p v-if="project.employer"><strong>I {{ project.current ? 'work' : 'worked'}} on this project as {{ project.employer.roleSentence ||  'an employee of' }} <a :href="project.employer.link">{{ project.employer.name }}</a> </strong> </p>
          <p v-for="projectText of $t(`projects.${project.i18nKey}.descriptionTexts`)" :key="projectText" >
            {{ projectText }}
            </p>
          <p v-if="project.disclaimerText"><strong>{{$t(project.disclaimerText)}}</strong></p>
          <hr class="my-3">
          <v-chip v-for="tag of project.tags" dark :color="tag.color" :key="`${project.title}-${tag.text}`">
            {{tag.text}}
          </v-chip>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn v-if="project.githubLink" color="grey lighten-2" :href="project.githubLink" target="_blank">Code&nbsp;<v-img src="/giticon-invert.png"></v-img></v-btn>
          <v-btn v-for="link of project.links" :key="link.text" dark :color="link.color ? link.color : '#006591'" :href="link.url" target="_blank">
            {{link.text}} 
            <v-img v-if="link.img" :src="link.img"></v-img>
            <v-icon v-if="!link.img" right dark>open_in_new</v-icon>

          </v-btn>
          <v-btn
          v-if="project.link"
            color="#006591"
            dark
            :href="project.link"
            target="_blank"
          >Visit<v-icon right dark>open_in_new</v-icon></v-btn> 
        </v-card-actions>
      </v-card>
</template>

<script>
export default {
  props: {
    project: Object,
    ProjectTypes: Object
  }
}
</script>