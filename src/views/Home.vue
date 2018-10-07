<template>
  <div>
    <Hero />
    <What />
    <Process />
    <Projects />

    <v-container>
      <v-layout row wrap py-5>
        <v-flex sm6 pa-4>
          <v-img src="../assets/ipads.png" data-aos="fade-right"></v-img>
        </v-flex>
        <v-flex sm6 pa-4>
          <h2 class="display-2 font-weight-thin">Cool Stuff</h2>
          <h4 class="headline my-1">Responsive Layout</h4>
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dolorem sequi temporibus aut expedita rerum delectus, et iusto tempora voluptatem quis.</p>
        </v-flex>
      </v-layout>
    </v-container>

    <section id="contact" class="grey lighten-3">
      <v-container>
        <v-layout row wrap py-5>
          <v-flex xs12 pt-4 text-xs-center>
            <h2 class="headline text-uppercase my-1">Get in touch</h2>
            <div class="subheading text-uppercase grey--text text--lighten-1">Lorem ipsum dolor sit amet</div>
          </v-flex>
        </v-layout>
        <v-layout row wrap pb-5>
          <v-flex sm12 md6 offset-md3>
            <v-form class="text-xs-center">
                <v-text-field type="text" label="Name" outline></v-text-field>
                <v-text-field type="email" label="Email" outline></v-text-field>
                <v-textarea outline label="Message"></v-textarea>
                <v-btn large class="white--text" color="primary" mx-5>Send message</v-btn>
            </v-form>

          </v-flex>
        </v-layout>
      </v-container>
    </section>
  </div>
</template>

<script>
import Hero from '../components/Hero.vue'
import What from '../components/What.vue'
import Process from '../components/Process.vue'
import Projects from '../components/Projects.vue'

export default {
  components: {
    Hero,
    What,
    Process,
    Projects
  },
  data () {
    return {
      offsetTop: 0,
      show: false
    }
  }
}
</script>

<style lang="scss">
  $nice-ease: cubic-bezier(.45,.16,0,.77);

  .titleAnim {
    animation: 1s blurIn ease;
  }
  @-webkit-keyframes blurIn {
    0% { 
      filter: blur(20px);
      }
    100% { 
      filter: blur(0);
      }
  }
   @-webkit-keyframes fadeIn {
    0% { 
      opacity: 0;
      }
    100% { 
      opacity: 1;
      }
  }
</style>
