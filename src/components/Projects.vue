<template>
    <section id="projects" class="grey lighten-3">
      <v-container>
        <v-layout row wrap py-5>
          <v-flex xs12 pt-4 text-xs-center>
            <h2 class="headline text-uppercase my-1">Recent Projects</h2>
            <div class="subheading text-uppercase grey--text text--lighten-1">Lorem ipsum dolor sit amet</div>
          </v-flex>
        </v-layout>
        <v-layout row wrap pb-5>
          <v-flex v-for="(project, index) in projects" :key="index.project" xs12 sm6 :class="{'py-2': $vuetify.breakpoint.xs, 'pa-2': $vuetify.breakpoint.sm, 'pa-3': $vuetify.breakpoint.mdAndUp}"> 
            <v-card data-aos="fade-up">
              <v-img class="white--text" height="200px" :src="project.image"></v-img>
              <v-card-title primary-title>
                <div>
                  <div class="headline">{{ project.title }}</div>
                  <div class="pt-2">{{ project.subtitle }}</div>
                </div>
              </v-card-title>
              <v-divider></v-divider>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn flat color="blue">Learn More</v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </section>
</template>

<script>
export default {
  data() {
    return {
      isVisible: true,
      prevRatio: 0,
      projects: [
        {
          image: require('../assets/servico1.jpg'),
          title: 'Sit Consectetur',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus exercitationem veniam quas eum sapiente vero sunt.',
          link: ''
        },
        {
          image: require('../assets/servico2.jpg'),
          title: 'Halycon Days',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus exercitationem veniam quas eum sapiente vero sunt.',
          link: ''
        },
        {
          image: require('../assets/servico3.jpg'),
          title: 'Adipisicing Elit',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus exercitationem veniam quas eum sapiente vero sunt.',
          link: ''
        },
        {
          image: require('../assets/servico1.jpg'),
          title: 'Natus Veniam',
          subtitle:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus exercitationem veniam quas eum sapiente vero sunt.',
          link: ''
        }
      ]
    }
  },
  methods: {
    
  }
};
</script>

