<template>
    <section id="process">
        <v-container>
            <v-layout py-5>
                <v-flex xs12 pt-4 text-xs-center>
                <h2 class="headline text-uppercase my-1">Our Work Process</h2>
                <div class="subheading text-uppercase grey--text text--lighten-1">Lorem ipsum dolor sit amet</div>
                </v-flex>
            </v-layout>
            <v-layout row wrap pb-5>
                <v-flex v-for="(process, index) in processes" :key="index.process" xs12 sm4 text-xs-center>
                <v-icon x-large color="grey darken-3" style="font-size: 80px;">{{ process.icon }}</v-icon>
                <h2 class="subheading text-uppercase my-1">{{ process.title }}</h2>
                <div class="subheading grey--text text--lighten-1">{{ process.subtitle }}</div>
                </v-flex>
            </v-layout>
        </v-container>
    </section>
</template>

<script>
export default {
  data() {
    return {
      isVisible: false,
      prevRatio: 0,
      processes: [
        {
          icon: 'desktop_mac',
          title: 'Design',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi, provident amet? Ad!'
        },
        {
          icon: 'dvr',
          title: 'Develop',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi, provident amet? Ad!'
        },
        {
          icon: 'photo_size_select_actual',
          title: 'Deploy',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi, provident amet? Ad!'
        }
      ]
    }
  },
  methods: {

  }
};
</script>
