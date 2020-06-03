<template>
  <v-row>
    <v-col>
      Test
    </v-col>
  </v-row>
</template>

<script>
  export default {
    data () {
      return {
        carousel: [
          {
            title: 'events',
            link: '/img/events.png',
          },
          {
            title: 'protesting',
            link: '/img/protesting.png',
          },
          {
            title: 'guides',
            link: '/img/guides.png',
          },
          {
            title: 'community',
            link: '/img/community.png',
          },
          {
            title: 'donate',
            link: '/img/donate.png',
          },
        ],
      }
    },
  }
</script>
