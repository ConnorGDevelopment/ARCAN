<template>
  <v-row>
    <v-col
      v-for="image in carousel"
      :id="image.title"
      :key="image.title"
      class="pa-0 carousel"
      :style="{width : image.width}"
      @mouseover="expand(image.index)"
      @mouseleave="shrink"
    >
      <v-img
        class="backgroundImage pt-2"
        :class="(image.width === '5%') ? 'align-start' : 'align-end'"
        :src="image.link"
      >
        <v-card class="transparent">
          <v-card-title
            class="display-1"
            :class="(image.width === '5%') ? 'vertical mx-auto' : ''"
          >
            {{ image.title }}
          </v-card-title>
          <v-card-subtitle
            v-if="image.width != '5%'"
            class="body-1 primary--text"
          >
            {{ image.subtitle }}
          </v-card-subtitle>
        </v-card>
      </v-img>
    </v-col>
  </v-row>
</template>

<style>
.vertical {
  writing-mode: vertical-rl;
  text-orientation: upright;
}
.carousel {
  min-height: calc(100vh - 64px);
}
</style>

<script>
  export default {
    data () {
      return {
        carousel: [
          {
            title: 'Events',
            index: 0,
            link: '/img/events.png',
            width: '20%',
            subtitle: 'This is where you\'ll find protests and other activist events.',
          },
          {
            title: 'Protesting',
            index: 1,
            link: '/img/protesting.png',
            width: '20%',
            subtitle: 'Learn about your rights as a protestor and how to stay safe at protests.',
          },
          {
            title: 'Guides',
            index: 2,
            link: '/img/guides.png',
            width: '20%',
            subtitle: 'Here you\'ll find resources on how to organize events, fundraisers, and petitions.',
          },
          {
            title: 'Community',
            index: 3,
            link: '/img/community.png',
            width: '20%',
            subtitle: 'Find POC-owned businesses and the ways you can support them.',
          },
          {
            title: 'Donate',
            index: 4,
            link: '/img/donate.png',
            width: '20%',
            subtitle: 'Make financial contributions to bail bond organizations like the Columbus Freedom Fund.',
          },
        ],
      }
    },
    methods: {
      expand (carouselIndex) {
        for (const item of this.carousel) {
          item.width = item.index === carouselIndex ? '80%' : '5%'
        }
      },
      shrink (carouselIndex) {
        for (const item of this.carousel) {
          item.width = '0%'
        }
      },
    },
  }
</script>
