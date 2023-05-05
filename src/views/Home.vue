<template>
  <v-container grid-list-xl class="home">
    <v-layout column justify-center align-center class="mt-5 pb-5">
      <vue-typer class="headline" :repeat="0" text="Karan Jain"></vue-typer>
      <vue-typer
        :text="text1"
        :repeat="Infinity"
        :shuffle="false"
        initial-action="erasing"
        :pre-type-delay="70"
        :type-delay="70"
        :pre-erase-delay="1980"
        :erase-delay="150"
        erase-style="select-back"
        :erase-on-complete="false"
        caret-animation="smooth"
        style="text-transform: math-auto;"
      ></vue-typer>
    </v-layout>
    <br />
    <v-layout row justify-center align-center wrap>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-flex xs12 sm12 md4 lg7 xl5>
          <v-card flat color="transparent" max-width="500">
            <v-card-title primary-title>
              <div>
                <h3 class="headline mb-0">
                  <span>About</span>
                  <span class="green--text">Me</span>
                </h3>
                <div>
                  <p>
                    Hello! I’m Karan Jain. Detail-oriented, analytical Lead
                    Software Engineer with more than 4 years of experience in
                    creating and executing innovative software solutions to
                    enhance business productivity. Highly experienced in all
                    aspects of the software development lifecycle and end-to-end
                    project management, from concept through to development and
                    delivery. Consistently recognized as a hands-on and
                    competent leader, skilled at coordinating cross-functional
                    teams in a fast-paced, deadline-driven environment to steer
                    timely project completion within budgetary constraints.
                    Seeking to involve with an organization to showcase my
                    potential and enhance my skills.
                  </p>
                </div>
              </div>
            </v-card-title>

            <v-card-actions class="hidden-sm-and-down">
              <v-btn
                v-for="icon in icons"
                :key="icon.icon"
                fab
                dark
                outline
                color="green"
                :href="icon.href"
                target="_blank"
              >
                <v-icon dark>{{ icon.icon }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-card-actions class="hidden-md-and-up justify-center">
              <v-btn
                v-for="icon in icons"
                :key="icon.icon"
                small
                fab
                dark
                outline
                color="green"
                :href="icon.href"
                target="_blank"
              >
                <v-icon dark>{{ icon.icon }}</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-flex
          xs10
          sm12
          md12
          lg9
          xl12
          style="margin-right: 10px; padding-right: 5px"
        >
          <img src="../assests/half.jpeg" />
        </v-flex>
      </v-layout>
    </v-layout>
  </v-container>
</template>

<script>
import { VueTyper } from 'vue-typer'

export default {
  metaInfo: {
    title: 'Home',
    titleTemplate: "%s ← Karan's Space",
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { charset: 'utf-8' },
      { property: 'og:title', content: "Karan' Space" },
      { property: 'og:site_name', content: "Karan' Space" },
      { property: 'og:type', content: 'website' },
      {
        property: 'og:image',
        content:
          'https://lh3.googleusercontent.com/hPIsg782gwv2NKVdqlNVDtDgpKWelaB4MYBJUVeKYO4jFkE5Q9oWaKjTqpS49cc9nsUP5t2oatADR3VKKSy0kKFgCLvT-H-GooqEzonzEXwRmz7um1lORU2MP3ezLboIBDwQ391-9f89dvJy4lD0E2po7Xiqd3fKKjGRks6CIIWUWDKwyeJqQKGm1N6BlPU_qAtN6jC5oR2Pk-sj4aEkfvxFoKbL8Pz2Qdn-sKCiP2Nid1nmg6rLLu9UzAzwdF8f7wv0MNxShEl6pyyur11oAdhtBvH9Lnfcu2nHsmTsJzk_ZloDmq9UhOHM8h5m83Wk3NBEOo6Xofc7z5hFvJqHUyPrUbmzUn42NbUYTp6sm0b29NpATrp3E04vxUPhc-DZznhwKwfB2epaoVBkP-FOXF0T4ea-w5R-GHubuLsCdr0Ab67JLJVhmahrY1lbVIrWArq782VM8q3zJczGe8U241-4v6bLCNjJKZq1od5Sp3am3McBxfi52l7xoF76n3PwnCPN6VKuUlB3Y5W3lIZfQXK3Ban1hhaN5nmzb4vwn4WYq58-p0Ax9aV7_PqloFXjS0SvUb_Mw8KjXiPDNuOUJtcTfJswQFH2yzfGL6HdvPSWTCh0uo8fpup6wK-NImwOgfpu8PET3jhtzs4YQQ-Ez7BUO7uzbmF99v9kOpZEu034YHFh7Ht6UXnYdF2JPNkznWXpLEsBsKsWhHa_nMr6Z50=w704-h937-no?authuser=0'
      }
    ]
  },
  components: {
    'vue-typer': VueTyper
  },
  data () {
    return {
      icons: [
        { href: 'https://github.com/JainKanu', icon: 'fab fa-github' },
        {
          href: 'https://www.linkedin.com/in/karan-jain-15b952179/',
          icon: 'fab fa-linkedin-in'
        },
        {
          href: 'https://www.facebook.com/karanjain0002/',
          icon: 'fab fa-facebook-f'
        },
        {
          href: 'https://www.instagram.com/karan.jain740/',
          icon: 'fab fa-instagram'
        }
      ],
      text1: [
        'Lead Software Engineer',
        'Front-End Developer',
        'Web Designer'
      ]
    }
  }
}
</script>
<style>
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }

  50% {
    transform: rotateZ(10deg);
  }
}

.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
  color: green;
}
.vue-typer .custom.char.selected {
  color: #e91e63;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: green;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #e91e63;
}
</style>
