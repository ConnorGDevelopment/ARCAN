<template>
  <v-col cols="4">
    <v-card class="accent">
      <v-card-title class="headline">
        Upcoming Events
      </v-card-title>
      <v-list-item
        v-for="event in events"
        :key="event.link"
        two-line
      >
        <v-list-item-content>
          <v-list-item-title class="subtitle">
            {{ event.title }}
          </v-list-item-title>
          <v-list-item-subtitle>
            {{ event.date }}
            <br>
            {{ event.time }}
            <br>
            {{ event.location }}
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-card>
  </v-col>
</template>

<script>
  export default {
    props: {
      events: Array,
    },
  }
</script>
