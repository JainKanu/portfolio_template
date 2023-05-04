<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mt-2">
          <span>GetIn</span>
          <span class="green--text">Touch</span>
        </h2>
        <div class="py-4 subheading font-weight-bold">
          <p class="m-0" style="width: fit-content">
            <v-icon size="35" color="green" left class=""
              >fas fa-map-marker-alt</v-icon
            >
            <span>Bathinda,&nbsp;</span>
            <span class="green--text">Punjab,&nbsp;India</span>
          </p>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <p
            class="m-0"
            style="width: fit-content; cursor: pointer"
            @click="sendEmail()"
          >
            <v-icon size="30" color="green" left>fas fa-envelope</v-icon>
            <span>karan.jain740@</span>
            <span class="green--text">icloud.com</span>
          </p>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <p
            class="m-0"
            style="width: fit-content; cursor: pointer"
            @click="callMe()"
          >
            <v-icon size="30" color="green" left>fas fa-phone</v-icon>
            <span>+91&nbsp;</span>
            <span class="green--text">78884 15250</span>
          </p>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <p class="m-0" style="width: fit-content">
            <v-icon size="30" color="green" left>fas fa-check</v-icon>
            <span>Freelance</span>
            <span class="green--text">Available</span>
          </p>
        </div>
      </v-flex>

      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mb-4">
          <span>Contact</span>
          <span class="green--text">Form</span>
        </h2>

        <form method="POST" action="https://formspree.io/f/xzbogpjr">
          <v-text-field
            name="name"
            color="green"
            background-color="transparent"
            v-model="name"
            :error-messages="nameErrors"
            label="Name"
            required
            @blur="$v.name.$touch()"
          ></v-text-field>
          <v-text-field
            type="email"
            color="green"
            background-color="transparent"
            name="email"
            v-model="email"
            :error-messages="emailErrors"
            label="E-mail"
            required
            @blur="$v.email.$touch()"
          ></v-text-field>
          <v-textarea
            color="green"
            background-color="transparent"
            :counter="200"
            :error-messages="bodyErrors"
            v-model="body"
            label="Textarea"
            name="body"
            @blur="$v.body.$touch()"
          ></v-textarea>
          <v-btn
            @click="submit"
            type="submit"
            color="green"
            class="white--text"
            :disabled="disableSubmitButton"
            >SEND MESSAGE</v-btn
          >
          <v-btn @click="clear">clear</v-btn>
        </form>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import { validationMixin } from 'vuelidate'
import {
  required,
  maxLength,
  email,
  minLength
} from 'vuelidate/lib/validators'
export default {
  metaInfo: {
    title: 'Contact',
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
  mixins: [validationMixin],
  validations: {
    name: { required, maxLength: maxLength(20) },
    email: { required, email },
    body: { minLength: minLength(10) }
  },
  data () {
    return {
      name: '',
      email: '',
      body: ''
    }
  },
  methods: {
    sendEmail () {
      window.location = 'mailto:karan.jain740@icloud.com'
    },
    callMe () {
      window.location = 'tel:+917888415250'
    },
    submit () {
      this.$v.$touch()
    },
    clear () {
      this.$v.$reset()
      this.name = ''
      this.email = ''
      this.body = ''
    }
  },
  computed: {
    disableSubmitButton () {
      if (
        (this.nameErrors && this.nameErrors.length) ||
        (this.emailErrors && this.emailErrors.length) ||
        (this.bodyErrors && this.bodyErrors.length)
      ) {
        return true
      } else {
        return false
      }
    },
    nameErrors () {
      const errors = []
      if (!this.$v.name.$dirty) return errors
      !this.$v.name.maxLength &&
        errors.push('Name must be at most 20 characters long')
      !this.$v.name.required && errors.push('Name is required.')
      return errors
    },
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Must be valid e-mail')
      !this.$v.email.required && errors.push('E-mail is required')
      return errors
    },
    bodyErrors () {
      const errors = []
      if (!this.$v.body.$dirty) return errors
      !this.$v.body.minLength &&
        errors.push('Text must be at least 10 characters long')
      return errors
    }
  }
}
</script>

<style lang="scss" scoped></style>
