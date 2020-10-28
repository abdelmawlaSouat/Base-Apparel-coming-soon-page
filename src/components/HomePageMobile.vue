<template>
  <div class="homepage-mobile">
      <section>
          <v-img
            :src="require('@/assets/logo.svg')"
            alt="Logo"
            width="150"
            class="logo"
          ></v-img>
          <v-img
            :src="require('@/assets/hero-desktop.jpg')"
            alt="Hero"
            width="100%"
            position="left top"
            height="50vh"
            class="hero-img"
          ></v-img>
          <div class="content">
            <h1 class="large-text">
              <span class="red-color">WE'RE</span>
              COMING SOON
            </h1>
            <p class="red-color">
              Hello fellow shoppers! We're currently building our
              new fashion store. Add your email below to stay
              up-to-date with announcements and our launch deals.
            </p>
            <v-form ref="form" v-model="valid">
              <div class="input-div">
                <v-text-field
                  outlined
                  v-model="email"
                  :rules="[rules.required, rules.email]"
                  class="red-color"
                  label="Email Address"
                  :success-messages="valid && emailSent ? 'Email Sent !' : ''"
                  required
                ></v-text-field>
                <img
                  v-show="!valid && email"
                  :src="require('@/assets/icon-error.svg')"
                  alt="Error"
                  class="error-icon"
                />
                <v-btn dark class="submit-btn" @click="validate()">
                  <v-icon>mdi-arrow-right</v-icon>
                </v-btn>
              </div>
            </v-form>
          </div>
      </section>
  </div>
</template>

<script>
export default {
  name: 'HomePageDesktop',
  data () {
    return {
      email: '',
      valid: true,
      emailSent: false,
      rules: {
        required: value => !!value || 'E-mail is required',
        email: value => /.+@.+\..+/.test(value) || 'Please provide a valid email'
      }
    }
  },
  methods: {
    validate () {
      this.$refs.form.validate()
      if (this.valid) this.emailSent = true
    }
  }
}
</script>

<style lang="css">

.homepage-mobile {
  font-family: "Josefin Sans";
  margin-bottom: 5rem;
}
.homepage-mobile .input-div {
  display: flex;
  margin-left: 1rem;
}
.v-input__control {
  width: 30vh;
}
.homepage-mobile .logo {
  margin: 2rem 1rem 2rem 1rem;
}
.homepage-mobile .error-icon {
  width: 20px !important;
  height: 20px !important;
  position: relative;
  left: -8vh;
  top: 2vh;
}
.homepage-mobile .submit-btn {
  position: relative;
  left: -7vh;
  width: 95px !important;
  height: 60px !important;
  border-radius: 5rem !important;
  background: linear-gradient(hsl(0, 80%, 86%), hsl(0, 74%, 74%)) !important;
}
.homepage-mobile .hero-img {
  margin-top: 2rem;
}
.homepage-mobile .content {
  padding-top: 3vh;
  margin-right: 1rem;
  margin-left: 1rem;
  text-align: center;
}
.homepage-mobile p {
  font-size: 1.1rem;
  margin-top: 2rem;
  margin-bottom: 2.5rem;
  line-height: 1.5rem;
}
.homepage-mobile h1 {
  font-weight: lighter;
  letter-spacing: 1.5rem;
  line-height: 4.5rem;
}
.homepage-mobile .large-text {
  font-size: 2.5rem;
}

</style>
