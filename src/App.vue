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
import TheHeader from './components/TheHeader'
import TheFooter from './components/TheFooter'

export default {
  name: 'App',
  metaInfo: {
    title: 'Home',
    titleTemplate: "%s ← Karan's Space",
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { name: 'description', content: "Karan Jain's Portfolio" },
      { charset: 'utf-8' },
      { property: 'og:title', content: "Karan' Space" },
      { property: 'og:site_name', content: "Karan' Space" },
      { property: 'og:type', content: 'website' },
      {
        property: 'og:image',
        content:
          'https://lh3.googleusercontent.com/hPIsg782gwv2NKVdqlNVDtDgpKWelaB4MYBJUVeKYO4jFkE5Q9oWaKjTqpS49cc9nsUP5t2oatADR3VKKSy0kKFgCLvT-H-GooqEzonzEXwRmz7um1lORU2MP3ezLboIBDwQ391-9f89dvJy4lD0E2po7Xiqd3fKKjGRks6CIIWUWDKwyeJqQKGm1N6BlPU_qAtN6jC5oR2Pk-sj4aEkfvxFoKbL8Pz2Qdn-sKCiP2Nid1nmg6rLLu9UzAzwdF8f7wv0MNxShEl6pyyur11oAdhtBvH9Lnfcu2nHsmTsJzk_ZloDmq9UhOHM8h5m83Wk3NBEOo6Xofc7z5hFvJqHUyPrUbmzUn42NbUYTp6sm0b29NpATrp3E04vxUPhc-DZznhwKwfB2epaoVBkP-FOXF0T4ea-w5R-GHubuLsCdr0Ab67JLJVhmahrY1lbVIrWArq782VM8q3zJczGe8U241-4v6bLCNjJKZq1od5Sp3am3McBxfi52l7xoF76n3PwnCPN6VKuUlB3Y5W3lIZfQXK3Ban1hhaN5nmzb4vwn4WYq58-p0Ax9aV7_PqloFXjS0SvUb_Mw8KjXiPDNuOUJtcTfJswQFH2yzfGL6HdvPSWTCh0uo8fpup6wK-NImwOgfpu8PET3jhtzs4YQQ-Ez7BUO7uzbmF99v9kOpZEu034YHFh7Ht6UXnYdF2JPNkznWXpLEsBsKsWhHa_nMr6Z50=w704-h937-no?authuser=0'
      },
      { property: 'og:description', content: "Karan Jain's Portfolio" }
    ]
  },
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
</style>
