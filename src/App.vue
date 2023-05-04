<template>
  <v-app :dark="goDark">
    <v-content>
      <v-container align-center>
        <TheHeader :goDark="goDark" @changeTheme="updateTheme($event)" />

        <transition
          name="router-animation"
          mode="out-in"
          enter-active-class="animated fadeIn fast"
          leave-active-class="animated fadeOut faster"
        >
          <router-view></router-view>
        </transition>
      </v-container>
    </v-content>
    <TheFooter />
  </v-app>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheFooter from './components/TheFooter.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    TheFooter
  },
  data () {
    return { goDark: false }
  },
  mounted () {
    let theme = localStorage.getItem('theme')
    this.goDark = JSON.parse(theme)
  },
  methods: {
    updateTheme (updatedTheme) {
      this.goDark = !updatedTheme
      localStorage.setItem('theme', JSON.stringify(this.goDark))
    }
  }
}
</script>
<style>
@import "./style/animate.min.css";
@import "./style/style.css";
/* width */
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #888;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>
