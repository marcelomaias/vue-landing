<template>
  <v-app v-scroll="onScroll">
    <v-navigation-drawer temporary v-model="drawer" enable-resize-watcher fixed app>
      <v-list>
        <v-list-tile @click="$vuetify.goTo('#what')">
          <v-list-tile-action>
            <v-icon class="black--text">build</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="black--text">What we do</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile @click="$vuetify.goTo('#process')">
          <v-list-tile-action>
            <v-icon class="black--text">view_list</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="black--text">Work Process</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile @click="$vuetify.goTo('#projects')">
          <v-list-tile-action>
            <v-icon class="black--text">bubble_chart</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="black--text">Projects</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile @click="$vuetify.goTo('#contact')">
          <v-list-tile-action>
            <v-icon class="black--text">chat_bubble</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="black--text">Contact</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <!-- <v-list-tile value="true" v-for="(link, i) in menuLinks" :key="i" :href="link.target">
          <v-list-tile-action>
            <v-icon v-html="link.icon" class="black--text"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="link.title" class="black--text"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile> -->
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed :flat="!isScrolling" :class="{ transparent: !isScrolling }">
      <v-toolbar-side-icon @click.stop="drawer = !drawer" class="hidden-md-and-up"></v-toolbar-side-icon>
      <v-flex sm2>
        <a href="#"><v-img class="logo" src="./assets/logo.png"></v-img></a>
      </v-flex>
      <!-- <v-toolbar-title v-text="title" class="text-uppercase font-weight-black" to="#"></v-toolbar-title> -->
      <v-spacer></v-spacer>
      <!-- {{ offsetTop }} -->
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat @click="$vuetify.goTo('#what')"><v-icon left dark>build</v-icon>What we do</v-btn>
        <v-btn flat @click="$vuetify.goTo('#process')"><v-icon left dark>view_list</v-icon>Work Process</v-btn>
        <v-btn flat @click="$vuetify.goTo('#projects')"><v-icon left dark>bubble_chart</v-icon>Projects</v-btn>
        <v-btn flat @click="$vuetify.goTo('#contact')"><v-icon left dark>chat_bubble</v-icon>Contact</v-btn>
        <!-- <v-btn flat v-for="(link, i) in menuLinks" :key="i" :href="link.target">
          <v-icon left dark v-html="link.icon"></v-icon>
          {{ link.title}}
        </v-btn> -->
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer height="auto" color="primary lighten-1">
      <v-layout justify-center row wrap>
        <v-btn v-for="(link, i) in menuLinks" :key="i" color="white" flat round :href="link.target">
          {{ link.title }}
        </v-btn>
        <v-flex primary lighten-2 py-3 text-xs-center white--text xs12>
          &copy;2018 — <strong>TheCompany</strong>
        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      drawer: false,
      offsetTop: 0,
      title: 'Company',
      type: 'selector',
      selector: '#what',
      menuLinks: [
      {
        icon: 'build',
        title: 'What we do',
        target: '#what'
      },
      {
        icon: 'view_list',
        title: 'Work Process',
        target: '#process'
      },
      {
        icon: 'bubble_chart',
        title: 'Projects',
        target: '#projects'
      },
      {
        icon: 'chat_bubble',
        title: 'Contact',
        target: '#contact'
      }
      ]
    }
  },
  methods: {
    onScroll () {
      this.offsetTop = window.pageYOffset || document.documentElement.scrollTop
    }
  },
  computed: {
    isScrolling () {
      return this.offsetTop > 100
    }
  }
}
</script>

