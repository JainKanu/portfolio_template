<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md5 lg6 xl6 class="mt-4 pt-4">
        <h2 class="mb-4 pl-4 pt-2">Education</h2>
        <v-card-text class="py-0">
          <v-timeline align-top dense>
            <v-timeline-item color="green" small>
              <v-layout pt-3>
                <v-flex xs4>
                  <div class="caption font-weight-bold green--text">
                    APRIL 2012 -
                  </div>
                  <div class="caption font-weight-bold green--text">
                    MARCH 2013
                  </div>
                </v-flex>
                <v-flex class="pl-2">
                  <strong>Secondary (10th Pass)</strong>
                  <div class="caption mb-2">Punjab school education board</div>
                </v-flex>
              </v-layout>
            </v-timeline-item>

            <v-timeline-item color="green" small>
              <v-layout pt-3>
                <v-flex xs4>
                  <div class="caption font-weight-bold green--text">
                    APRIL 2014 -
                  </div>
                  <div class="caption font-weight-bold green--text">
                    MARCH 2015
                  </div>
                </v-flex>
                <v-flex class="pl-2">
                  <strong>Higher Secondary (12th Pass)</strong>
                  <div class="caption mb-2">Punjab school education board</div>
                </v-flex>
              </v-layout>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-flex>
      <v-flex xs12 sm12 md4 lg6 xl6 class="mt-4 pt-2">
        <h2 class="mb-4 pl-4">Experience</h2>
        <v-card-text class="py-0">
          <v-timeline align-top dense>
            <v-timeline-item color="green" small>
              <v-layout pt-3>
                <v-flex xs4>
                  <div class="caption font-weight-bold green--text">
                    AUGUST 2021 -
                  </div>
                  <div class="caption font-weight-bold green--text">
                    PRESENT
                  </div>
                </v-flex>
                <v-flex class="pl-2">
                  <strong>Lead Software Engineer</strong>
                  <div class="caption mb-2">Albanero Dev Pvt. Ltd.</div>
                </v-flex>
              </v-layout>
            </v-timeline-item>

            <v-timeline-item color="green" small>
              <v-layout pt-3>
                <v-flex xs4>
                  <div class="caption font-weight-bold green--text">
                    JULY 2019 -
                  </div>
                  <div class="caption font-weight-bold green--text">
                    AUGUST 2021
                  </div>
                </v-flex>
                <v-flex class="pl-2">
                  <strong>Senior Web Developer</strong>
                  <div class="caption mb-2">
                    Get Launched Solutions Pvt. Ltd.
                  </div>
                </v-flex>
              </v-layout>
            </v-timeline-item>
            <v-timeline-item color="green" small>
              <v-layout pt-3>
                <v-flex xs4>
                  <div class="caption font-weight-bold green--text">
                    SEPTEMBER 2018 -
                  </div>
                  <div class="caption font-weight-bold green--text">
                    JUNE 2019
                  </div>
                </v-flex>
                <v-flex class="pl-2">
                  <strong>Freelance Frontend Developer</strong>
                  <div class="caption mb-2">Remote</div>
                </v-flex>
              </v-layout>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-flex>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
          <h2>
            <span>Coding</span>
            <span class="green--text">Skills</span>
          </h2>
          <br />
          <strong>VUE/NUXT</strong>
          <v-progress-linear
            v-model="vueNuxt"
            :buffer-value="bufferValue"
            color="green"
            height="16"
          ></v-progress-linear>
          <strong>HTML/CSS</strong>
          <v-progress-linear
            v-model="htmlCss"
            :buffer-value="bufferValue"
            color="green"
            height="16"
          ></v-progress-linear>
          <strong>JavaScript</strong>
          <v-progress-linear
            v-model="javaScript"
            :buffer-value="bufferValue"
            color="green"
            height="16"
          ></v-progress-linear>
        </v-flex>
        <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
          <h2>
            <span>&nbsp;</span>
          </h2>
          <br />
          <strong>TypeScript</strong>
          <v-progress-linear
            v-model="typeScript"
            :buffer-value="bufferValue"
            color="green"
            height="16"
          ></v-progress-linear>
          <strong>Docker</strong>
          <v-progress-linear
            v-model="docker"
            :buffer-value="bufferValue"
            color="green"
            height="16"
          ></v-progress-linear>
          <strong>React</strong>
          <v-progress-linear
            v-model="react"
            :buffer-value="bufferValue"
            color="green"
            height="16"
          ></v-progress-linear>
        </v-flex>
        <div class="mt-4 pt-2">
          <v-btn
            href="https://drive.google.com/file/d/1Z1caCsYXIjMXrly6q4FqjQe9DfJ8T-Xg/view?usp=sharing"
            target="_blank"
            download
            color="green"
            dark
            large
          >
            Download Resume
            <v-icon right dark>fas fa-file-download</v-icon>
          </v-btn>
        </div>
      </v-layout>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-flex xs12 sm12 md12 lg12 xl12>
          <h2 class="pl-4">
            <span>My</span>
            <span class="green--text">Services</span>
          </h2>
        </v-flex>
        <v-flex
          v-for="service in services"
          :key="service.src"
          xs6
          sm3
          md3
          lg3
          xl3
        >
          <v-card
            hover
            flat
            color="transparent"
            :style="{ cursor: 'context-menu' }"
          >
            <v-card-title></v-card-title>
            <v-card-title></v-card-title>
            <v-img
              :src="service.src"
              height="100"
              aspect-ratio="2.75"
              :alt="'Karan do ' + service.title"
              lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
              contain
            ></v-img>
            <v-card-title class="justify-center">
              <v-flex text-xs-center subheading font-weight-bold>
                {{ service.title }}
              </v-flex>
            </v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: 'Resume',
    titleTemplate: "%s ← Karan's Space",
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          'Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End'
      },
      { charset: 'utf-8' },
      { property: 'og:title', content: "Karan' Space" },
      { property: 'og:site_name', content: "Karan' Space" },
      { property: 'og:type', content: 'website' },
      {
        property: 'og:image',
        content:
          'https://lh3.googleusercontent.com/hPIsg782gwv2NKVdqlNVDtDgpKWelaB4MYBJUVeKYO4jFkE5Q9oWaKjTqpS49cc9nsUP5t2oatADR3VKKSy0kKFgCLvT-H-GooqEzonzEXwRmz7um1lORU2MP3ezLboIBDwQ391-9f89dvJy4lD0E2po7Xiqd3fKKjGRks6CIIWUWDKwyeJqQKGm1N6BlPU_qAtN6jC5oR2Pk-sj4aEkfvxFoKbL8Pz2Qdn-sKCiP2Nid1nmg6rLLu9UzAzwdF8f7wv0MNxShEl6pyyur11oAdhtBvH9Lnfcu2nHsmTsJzk_ZloDmq9UhOHM8h5m83Wk3NBEOo6Xofc7z5hFvJqHUyPrUbmzUn42NbUYTp6sm0b29NpATrp3E04vxUPhc-DZznhwKwfB2epaoVBkP-FOXF0T4ea-w5R-GHubuLsCdr0Ab67JLJVhmahrY1lbVIrWArq782VM8q3zJczGe8U241-4v6bLCNjJKZq1od5Sp3am3McBxfi52l7xoF76n3PwnCPN6VKuUlB3Y5W3lIZfQXK3Ban1hhaN5nmzb4vwn4WYq58-p0Ax9aV7_PqloFXjS0SvUb_Mw8KjXiPDNuOUJtcTfJswQFH2yzfGL6HdvPSWTCh0uo8fpup6wK-NImwOgfpu8PET3jhtzs4YQQ-Ez7BUO7uzbmF99v9kOpZEu034YHFh7Ht6UXnYdF2JPNkznWXpLEsBsKsWhHa_nMr6Z50=w704-h937-no?authuser=0'
      },
      {
        property: 'og:description',
        content:
          'Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End'
      }
    ]
  },
  data () {
    return {
      value: 0,
      vueNuxt: 0,
      htmlCss: 0,
      javaScript: 0,
      typeScript: 0,
      docker: 0,
      react: 0,
      bufferValue: 100,
      interval: 0,
      services: [
        {
          src: 'https://i.imgur.com/GvTt5GG.png',
          title: 'Web Development'
        },
        {
          src: 'https://i.imgur.com/g74mGuU.png',
          title: 'Web Design'
        }
      ]
    }
  },
  mounted () {
    this.startBuffer()
  },

  beforeDestroy () {
    clearInterval(this.interval)
  },

  methods: {
    startBuffer () {
      this.interval = setInterval(() => {
        this.vueNuxt = 90
        this.htmlCss = 90
        this.javaScript = 80
        this.typeScript = 70
        this.docker = 80
        this.react = 60
      }, 800)
    }
  }
}
</script>
<style>
.v-img--reveal {
  opacity: 0.3;
}
</style>
