<template>
  <v-layout
    column
    justify-center
    align-center
  >
  <PageTitle upperCase titleText="Projects"></PageTitle>
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-xs-center">
        <div class="text-xl-center">All projects I have worked on except WordPress projects have used <strong>Git</strong> for version management. </div>
        <br/>
        Technologies I have used/developed for:
        <br/>
        <br/>
        <v-item-group multiple>
            <v-item v-for="tag of tags" :key="`tag-${tag.text}`" >
              <v-chip
                slot-scope="{ active, toggle }"
                :selected="active"
                @click="toggle"
                :color="tag.color ? tag.color : undefined"
                dark
              >
                {{tag.text}}
              </v-chip>
            </v-item>
        </v-item-group>
      </div>
      
      <PageTitle titleText="Professional" subText="Projects I have worked on as a part of employment or professional training"></PageTitle>
      <ProjectCard v-for="project of projects" :project="project" :key="project.title" :ProjectTypes="ProjectTypes" />

      <PageTitle titleText="Prototypes etc." subText="Projects 100% written by myself for learning or educational purposes"></PageTitle>
      <ProjectCard v-for="project of prototypes" :project="project" :key="project.title" :ProjectTypes="ProjectTypes" />

    </v-flex>
  </v-layout>
</template>

<style>
.project-card {
  margin: 2em 0;
}
</style>

<script>
const tags = {
  ng: {
    text: "Angular",
    color: "red lighten-1"
  },
  ngjs: {
    text: "AngularJS",
    color: "red lighten-1"
  },
  react: {
    text: "React",
    color: "blue lighten-1"
  },
  vue: {
    text: "Vue",
    color: "teal"
  },
  redux: {
    text: "Redux",
    color: "purple"
  },
  reduxObservable: {
    text: "Redux-Observable",
    color: "pink lighten-2"
  },
  es6: {
    text: "Javascript/ES6",
    color: "yellow darken-3",
  },
  typeScript: {
    text: "TypeScript",
    color: "indigo darken-3",
  },
  nodeJs: {
    text: "NodeJS",
    color: "green darken-2"
  },
  express: {
    text: "Express",
  },
  jQuery: {
    text: "jQuery",
    color: "blue"
  },
  rxjs: {
    text: "RxJs",
    color: "pink lighten-2"
  },
  java: {
    text: "Java",
    color: "cyan darken-2"
  },
  sass: {
    text: "Sass",
    color: "pink darken-1"
  },
  wordpress: {
    text: "Wordpress",
    color: "blue darken-1"
  },
  css: {
    text: "CSS",
    color: "blue"

  },
  html: {
    text: "HTML5",
    color: "orange darken-2"
  },
  unity: {
    text: "Unity3D",
  },
  csharp: {
    text: "C#",
    color: "purple darken-1"
  },
  android: {
    text: "Android",
    color: "light-green darken-1"
  },
  ios: {
    text: "iOS"
  },
  nuxt: {
    text: "Nuxt",
    color: "teal"

  },
  vuetify: {
    text: "Vuetify",
    color: "teal"
  },
  highcharts: {
    text: "Highcharts",
    color: "indigo",
  }
}

const employers = {
  dfind: {
    name: "Dfind Consulting",
    link: "https://www.dfindconsulting.no/",
  },
  buypass: {
    name: "Buypass",
    link: "https://www.buypass.no/"
  },
  embassy: {
    name: "the Royal Norwegian Embassy in Japan",
    link: "https://www.norway.no/ja/japan",
    roleSentence: "a trainee at"
  }
}

const ProjectTypes = {
  Professional: "Professional",
  Hobby: "Hobby",
  Independent: "Independent",
  Student: "Student",
}

const herokuDisclaimer = "herokuDisclaimer"

import PageTitle from '~/components/PageTitle.vue';
import ProjectCard from '~/components/ProjectCard.vue';



export default {
  components: {
    PageTitle,
    ProjectCard
  },
    data () {
      return {
        tags,
        ProjectTypes,
        projects: [
          {
            type: ProjectTypes.Professional,
            current: true,
            title: "Storebrand",
            start: "January 2019",
            end: "Current",
            logo: {
              isTitle: true,
              url: "/logos/storebrandlogo.svg"
            },
            employer: employers.dfind,
            i18nKey: "storebrand",
            descriptionTexts: ["I work on a pension application at Storebrand, one of Norway's largest and oldest private financial companies.", "Is nice!!!"],
            disclaimerText: "The project I'm working on requires logging in with a Norwegian social security number",
            tags: [tags.ng,
              tags.typeScript,
            tags.rxjs,
            tags.sass,
            tags.highcharts
            
            ],
            link: "https://www.storebrand.no/en"
          },
          {
            type: ProjectTypes.Professional,
            title: "Husbanken",
            start: "August 2018",
            end: "December 2018",
            logo: {
              isTitle: true,
              url: "/logos/husbankenlogo.png"
            },
            i18nKey: "husbanken",
            employer: employers.dfind,
            descriptionTexts: [
              "I worked on an application system for Husbanken, a Norwegian public welfare bank that specializes in loans to public employees and individuals with financial problems.",
            ],
            disclaimerText: "The project I worked on requires logging in with a Norwegian social security number",
            tags: [
              tags.ng,
              tags.ngjs,
              tags.typeScript,
              tags.rxjs,
              tags.java,
              tags.sass,
            ],
            link: "https://www.husbanken.no/english/"
          },
          {
            type: ProjectTypes.Professional,
            title: "Norsk Tipping",
            start: "February 2017",
            end: "July 2018",
            logo: {
              isTitle: true,
              url: "/logos/norsktippinglogo.png"
            },
            employer: employers.buypass,
            i18nKey: "norskTipping",

            descriptionTexts: [
              "Bla bla norsk tipping"
            ],
            link : "https://www.norsk-tipping.no/",
            tags: [
              tags.react,
              tags.es6,
              tags.redux,
              tags.reduxObservable,
              tags.rxjs,
              tags.nodeJs,
              tags.express,
              tags.sass,
            ]
          },
          
          {
            type: ProjectTypes.Professional,
            title: "Energy Science Week 2015",
            start: "January 2015",
            end: "June 2015",
            link: "http://injapan.no/energy2015/",
            logo: {
              isTitle: true,
              url: "/logos/energyscienceweeklogo.jpg"
            },
            i18nKey: "embassy",
            employer: employers.embassy,

            tags: [
              tags.wordpress,
              tags.css,
              tags.html
            ]
          },
          {
            type: ProjectTypes.Professional,
            title: "Gintel",
            start: "February 2013",
            end: "June 2013",
            i18nKey: "gintel",

            logo: {
              isTitle: true,
              url: "/logos/gintellogo.png",
            },
            link: "https://www.gintel.com/",
            tags: [
              tags.java
            ]
          },
          
        ],
        prototypes: [
          {
            type: ProjectTypes.Independent,
            title: "Super Pipe Racer",
            start: "August 2016",
            end: "December 2016",
            i18nKey: "superPipeRacer",
            links: [{
              url: "https://itunes.apple.com/us/app/super-pipe-racer/id1165358265?mt=8",
              text: "iOS",
            },
            {
              url: "https://play.google.com/store/apps/details?id=com.Holdaas.SuperPipeRacer&hl=en",
              text: "Android",
            }
            ],
            githubLink: "https://github.com/larsdood/Super-Pipe-Racer",
            tags: [
              tags.unity,
              tags.csharp,
              tags.android,
              tags.ios
            ]
          },
          {
            type: ProjectTypes.Student,
            title: "Master Thesis",
            start: "July 2015",
            end: "January 2016",
            i18nKey: "masterThesis",
            githubLink: "https://github.com/larsdood/masterprosjekt",
            tags: [
              tags.java
            ]
          },
          {
            type: ProjectTypes.Hobby,
            title: "This website",
            i18nKey: "holdaascom",
            logo: {
              isTitle: true,
              url: "/logos/holdaaslogo.png",
            },
            tags: [
              tags.vue,
              tags.nuxt,
              tags.vuetify
            ]
          },
          {
            type: ProjectTypes.Hobby,
            title: "Tekwerk",
            i18nKey: "tekwerk",
            logo: {
              isTitle: true,
              url: "/logos/tekwerklogo.png"
            },
            tags: [
              tags.react
            ],
            githubLink: "https://github.com/larsdood/tekwerk",
            links: [ {
              url: "https://tekwerk.herokuapp.com/",
              text: "Prototype",
              color: "deep-purple darken-1"
            }
            ],
            disclaimerText: herokuDisclaimer
          },
          {
            type: ProjectTypes.Hobby,
            title: "Crypto Trader",
            logo: {
              isTitle: true,
              url: "/logos/cryptotraderlogo.PNG",
            },
            i18nKey: "cryptoTrader",
            githubLink: "https://github.com/larsdood/virtual_crypto_trading_site",
            links: [ {
              url: "https://virtual-crypto-trading-app.herokuapp.com/",
              text: "Prototype",
              color: "deep-purple darken-1"
            }],
            disclaimerText: herokuDisclaimer
          }
        ]
      }
    },
  }
</script>