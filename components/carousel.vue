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
        class="backgroundImage"
        :src="image.link"
      />
      </v-hover>
    </v-col>
  </v-row>
</template>

<style>
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
            title: 'events',
            index: 0,
            link: '/img/events.png',
            width: '20%',
          },
          {
            title: 'protesting',
            index: 1,
            link: '/img/protesting.png',
            width: '20%',
          },
          {
            title: 'guides',
            index: 2,
            link: '/img/guides.png',
            width: '20%',
          },
          {
            title: 'community',
            index: 3,
            link: '/img/community.png',
            width: '20%',
          },
          {
            title: 'donate',
            index: 4,
            link: '/img/donate.png',
            width: '20%',
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
