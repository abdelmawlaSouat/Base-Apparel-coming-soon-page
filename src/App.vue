<template>
  <div>
      <HomePageMobile v-if="$vuetify.breakpoint.smAndDown" />
      <HomePageDesktop v-else />
  </div>
</template>

<script>
import HomePageDesktop from './components/HomePageDesktop'
import HomePageMobile from './components/HomePageMobile'
export default {
  name: 'App',
  components: {
    HomePageDesktop,
    HomePageMobile
  }
}
</script>

<style lang="css">
@font-face {
  font-family: "Josefin Sans";
  src: local("Josefin Sans"),
  url(./fonts/JosefinSans-Regular.ttf) format("truetype");
}

:root {
  --desaturated-red: hsl(0, 36%, 70%);
  --soft-red: hsl(0, 93%, 68%);
}
.theme--light.v-text-field--outlined:not(.v-input--is-focused):not(.v-input--has-state) > .v-input__control > .v-input__slot fieldset {
  color: var(--desaturated-red) !important;
  border-radius: 25px;
}
.v-input--is-focused {
  color: var(--desaturated-red) !important;
  border-radius: 25px !important;
}
.theme--light.v-label, .theme--light.v-input input, .theme--light.v-input textarea {
  color: var(--desaturated-red) !important;
}

.v-input--has-state.v-text-field--is-booted.v-text-field--enclosed.v-text-field--outlined {
  color: var(--desaturated-red) !important;
  border-radius: 25px !important;
}
.v-messages {
  font-size: 1rem !important;
  margin-top: 5px;
}
.v-messages.theme--light.error--text {
  color: red !important;
}
.v-messages.theme--light.success--text {
  color: green !important;
}
.red-color {
  color: var(--desaturated-red);
}

</style>
