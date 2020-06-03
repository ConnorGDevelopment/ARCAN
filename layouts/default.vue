<template>
  <v-app>
    <v-app-bar
      app
      class="secondary"
    >
      <v-toolbar-title
        :style="{'max-height' : '100%'}"
        class="d-flex px-2 headline"
      >
        Athens Radical Community Activist Network
      </v-toolbar-title>
      <v-spacer />
      <v-toolbar-items v-show="$vuetify.breakpoint.lgAndUp">
        <v-btn
          v-for="link in links"
          :key="link.url"
          v-bind="links"
          text
          nuxt
          class="title text-capitalize px-2 text--primary"
          :to="link.url"
        >
          {{ link.text }}
        </v-btn>
      </v-toolbar-items>
      <v-menu
        v-show="$vuetify.breakpoint.mdAndDown"
        offset-y
        nudge-bottom="6"
      >
        <template v-slot:activator="{on}">
          <v-btn
            v-show="$vuetify.breakpoint.mdAndDown"
            icon
            v-on="on"
          >
            <v-icon>
              mdi-menu
            </v-icon>
          </v-btn>
        </template>
        <v-list class="secondary">
          <v-list-item
            v-for="link in links"
            :key="link.url"
            v-bind="links"
          >
            <v-btn
              v-ripple="{ 'class' : 'accent--text'}"
              text
              nuxt
              :to="link.url"
              class="title text-capitalize px-2 text--primary"
            >
              {{ link.text }}
            </v-btn>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-content class="secondary">
      <v-container
        fluid
        class="pa-0"
      >
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        title: 'Vuetify.js',
        links: [
          {
            url: '/',
            text: 'Home',
          },
          {
            url: '/events',
            text: 'Events',
          },
          {
            url: '/protest',
            text: 'Protesting',
          },
          {
            url: '/guides',
            text: 'Guides',
          },
          {
            url: '/community',
            text: 'Community',
          },
          {
            url: '/donate',
            text: 'Donate',
          },
        ],
      }
    },
  }
</script>
