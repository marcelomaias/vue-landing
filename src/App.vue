<template>
  <v-app v-scroll="onScroll">
    <v-navigation-drawer
      temporary
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in menuItems"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed flat dark color="transparent">
      <v-toolbar-side-icon @click.stop="drawer = !drawer" class="hidden-md-and-up"></v-toolbar-side-icon>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      {{ offsetTop }}
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat v-for="(item, i) in menuItems" :key="i">
          <v-icon left dark v-html="item.icon"></v-icon>
          {{ item.title}}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer app>
      <span>&copy; 2017</span>
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
      scrolling: false,
      menuItems: [{
        icon: 'bubble_chart',
        title: 'Inspire'
      }],
      title: 'Awesome Landing'
    }
  },
  methods: {
    onScroll () {
      this.offsetTop = window.pageYOffset || document.documentElement.scrollTop
      // if(this.offsetTop > 100) {
      //   scrolling: true
      // }
    }
  }
}
</script>
