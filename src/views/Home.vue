<template>
  <v-container grid-list-xl>
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
      ></vue-typer>
    </v-layout>
    <br />
    <v-layout row justify-center align-center wrap>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-flex xs12 sm12 md4 lg5 xl5>
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
                    teams in a fastpaced, deadline-driven environment to steer
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
          xs12
          sm12
          md12
          lg12
          xl12
          style="margin-right: 10px; padding-right: 5px"
        >
          <img src="../assests/pic.jpg" :height="350" :width="350" />
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
      { name: 'description', content: "Karan Jain's Portfolio" },
      { charset: 'utf-8' },
      { property: 'og:title', content: "Karan' Space" },
      { property: 'og:site_name', content: "Karan' Space" },
      { property: 'og:type', content: 'website' },
      {
        property: 'og:image',
        content:
          'https://lh3.googleusercontent.com/hAf7sB2i5cvC6vb9I8YKSFh2GjV8WKbfpl0yhTM36JZPhe129kf3wbfsgwUuVVz8dHyo4j4Tgxx0-g9vaeZ3kpgDc94CauBuCTknZ4YNagCm436UUad8hRXlyLsgJMzZ0xzLCC7k2KGW5x24yekOvXr63ugjUKy2QnoUIalM7bCBfuoe77CG7dHxlu-3tA_uLEl01PYnaS_LDJn0npdDzN67p9JyP2rQQ1g0uAcyqJTgtc1hStA7UwlmE5s8fxOl1HlKVBbOQ2VH94wEpXoWM1w-RVwY2gRBu8jEalQtdyXolxZJ1FHnrcX4V0rLO3ArHzbaE4Qx9NWM6SEc2PxVH7p9Yju6Gyl4mwnMqIkHeVflfV_VnwoXSZFvefQKA8JMJO73uS8B6o4f4QPzXFfXZDh6bBp9LAwJrS7hKhCrDZJ1CA7EqhWFsGuoI7UEdNuj55M2KMqS3RGs0IX4xQtjOgiUEi-A5GFnQO8gunO8qouBxlXsEgynZJi8pRVORweTOfBbSiYu8gECePa44XmRC6LfT1rp7FYfue6_VbWdPtK25zvxe0LIyExjjaSHYjOCYC4HwCYGkoT88J-RnmnbQ7zlyNpDEuQt0TWQNzmqeC6PlMm1uCXJ8hWtxaD32LLchlJ1GdTKb6kUAGS3WFbqHOg7KV-MbihN7r2uqBK6czdrvrdiRBkFvoTZROxwOaeQ7J6_vm3K4tUZ-1zjIPdeJxy8=s600-no?authuser=0'
      },
      { property: 'og:description', content: "Karan Jain's Portfolio" }
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
      text1: ['Lead Front-End Engineer', 'Senior Web Developer', 'Web Designer']
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
