<template>
    <section id="what" class="grey lighten-3">
      <v-container>
        <v-layout row wrap py-5>
          <v-flex xs12 pa-4 text-xs-center>
            <h2 class="headline text-uppercase my-1">What we do</h2>
            <div class="subheading text-uppercase grey--text text--lighten-1">Lorem ipsum dolor sit amet</div>
          </v-flex>
          <v-flex v-for="(service, index) in services" :key="index.service" xs12 md6 :class="{'py-2': $vuetify.breakpoint.smAndDown, 'pa-3': $vuetify.breakpoint.mdAndUp}">
            <v-card data-aos="fade-up">
                <v-layout>
                  <v-flex xs5>
                    <v-img :src="service.image" height="200px" > </v-img>
                  </v-flex>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="subheading text-uppercase mb-2">{{ service.title }}</div>
                        <div class="grey--text">{{ service.subtitle }}</div>
                      </div>
                    </v-card-title>
                    <v-card-actions>
                      <v-spacer></v-spacer>
                      <v-btn flat>Learn More</v-btn>
                    </v-card-actions>
                  </v-flex>
                </v-layout>
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
      services: [
        {
          image: require('../assets/servico1.jpg'),
          title: 'Service One',
          subtitle: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque necessitatibus aspernatur explicabo voluptas.'
        },
        {
          image: require('../assets/servico2.jpg'),
          title: 'Service Two',
          subtitle: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque necessitatibus aspernatur explicabo voluptas.'
        },
        {
          image: require('../assets/servico3.jpg'),
          title: 'Service Three',
          subtitle: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque necessitatibus aspernatur explicabo voluptas.'
        },
        {
          image: require('../assets/servico4.jpg'),
          title: 'Service Four',
          subtitle: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque necessitatibus aspernatur explicabo voluptas.'
        }
      ],
    }
  }
}
</script>
