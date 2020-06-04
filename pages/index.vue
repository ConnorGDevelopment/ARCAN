<template>
  <v-container
    fluid
    class="pt-0 secondary"
  >
    <carousel />
    <v-row>
      <event-module :events="events" />
    </v-row>
  </v-container>
</template>

<style>
.v-card__text, .v-card__title, .v-card__subtitle {
  word-break: normal !important;
}
.backgroundImage {
  background-size: cover;
  background-position: center;
  height: calc(100vh - 64px);
}
</style>

<script>
  export default {
    async asyncData ({ $content }) {
      const events = await $content('events').fetch()
      console.log(events)
      return {
        events,
      }
    },
  }
</script>
