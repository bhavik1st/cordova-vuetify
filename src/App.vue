<template>
  <v-app light>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      enable-resize-watcher
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon light v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed>
      <v-toolbar-side-icon @click.stop="drawer = !drawer" light></v-toolbar-side-icon>
      <v-btn
        icon
        light
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-btn
        icon
        light
        @click.stop="clipped = !clipped"
      >
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn
        icon
        light
        @click.stop="fixed = !fixed"
      >
        <v-icon>remove</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        icon
        light
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>
    <main>
      <v-container fluid>
        <v-slide-y-transition mode="out-in">
          <v-layout column align-center>
            <img src="/static/v.png" alt="Vuetify.js" class="mb-5">
            <blockquote>
              &#8220;First, mantap solve the problem. Then, write the code.&#8221;
              <footer>
                <small>
                  <em>&mdash;John Johnson</em>
                </small>
              </footer>
            </blockquote>
          </v-layout>
        </v-slide-y-transition>
      </v-container>
    </main>
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
    >
      <v-list>
        <v-list-tile @click="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed">
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'bubble_chart', title: 'Inspire' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>

<style>
/* roboto-300 - latin */
  @font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 300;
    src: url('/static/fonts/roboto-v16-latin-300.eot'); /* IE9 Compat Modes */
    src: local('Roboto Light'), local('Roboto-Light'),
        url('/static/fonts/roboto-v16-latin-300.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/static/fonts/roboto-v16-latin-300.woff2') format('woff2'), /* Super Modern Browsers */
        url('/static/fonts/roboto-v16-latin-300.woff') format('woff'), /* Modern Browsers */
        url('/static/fonts/roboto-v16-latin-300.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/static/fonts/roboto-v16-latin-300.svg#Roboto') format('svg'); /* Legacy iOS */
  }
  /* roboto-regular - latin */
  @font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    src: url('/static/fonts/roboto-v16-latin-regular.eot'); /* IE9 Compat Modes */
    src: local('Roboto'), local('Roboto-Regular'),
        url('/static/fonts/roboto-v16-latin-regular.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/static/fonts/roboto-v16-latin-regular.woff2') format('woff2'), /* Super Modern Browsers */
        url('/static/fonts/roboto-v16-latin-regular.woff') format('woff'), /* Modern Browsers */
        url('/static/fonts/roboto-v16-latin-regular.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/static/fonts/roboto-v16-latin-regular.svg#Roboto') format('svg'); /* Legacy iOS */
  }
  /* roboto-500 - latin */
  @font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 500;
    src: url('/static/fonts/roboto-v16-latin-500.eot'); /* IE9 Compat Modes */
    src: local('Roboto Medium'), local('Roboto-Medium'),
        url('/static/fonts/roboto-v16-latin-500.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/static/fonts/roboto-v16-latin-500.woff2') format('woff2'), /* Super Modern Browsers */
        url('/static/fonts/roboto-v16-latin-500.woff') format('woff'), /* Modern Browsers */
        url('/static/fonts/roboto-v16-latin-500.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/static/fonts/roboto-v16-latin-500.svg#Roboto') format('svg'); /* Legacy iOS */
  }
  /* roboto-700 - latin */
  @font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    src: url('/static/fonts/roboto-v16-latin-700.eot'); /* IE9 Compat Modes */
    src: local('Roboto Bold'), local('Roboto-Bold'),
        url('/static/fonts/roboto-v16-latin-700.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/static/fonts/roboto-v16-latin-700.woff2') format('woff2'), /* Super Modern Browsers */
        url('/static/fonts/roboto-v16-latin-700.woff') format('woff'), /* Modern Browsers */
        url('/static/fonts/roboto-v16-latin-700.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/static/fonts/roboto-v16-latin-700.svg#Roboto') format('svg'); /* Legacy iOS */
  }

  @font-face {
    font-family: 'Material Icons';
    font-style: normal;
    font-weight: 400;
    src: url('/static/fonts/MaterialIcons-Regular.eot'); /* For IE6-8 */
    src: local('Material Icons'),
      local('MaterialIcons-Regular'),
      url('/static/fonts/MaterialIcons-Regular.woff2') format('woff2'),
      url('/static/fonts/MaterialIcons-Regular.woff') format('woff'),
      url('/static/fonts/MaterialIcons-Regular.ttf') format('truetype');
  }
  .material-icons {
    font-family: 'Material Icons';
    font-weight: normal;
    font-style: normal;
    font-size: 24px;  /* Preferred icon size */
    display: inline-block;
    line-height: 1;
    text-transform: none;
    letter-spacing: normal;
    word-wrap: normal;
    white-space: nowrap;
    direction: ltr;

    /* Support for all WebKit browsers. */
    -webkit-font-smoothing: antialiased;
    /* Support for Safari and Chrome. */
    text-rendering: optimizeLegibility;

    /* Support for Firefox. */
    -moz-osx-font-smoothing: grayscale;

    /* Support for IE. */
    font-feature-settings: 'liga';
  }
</style>
<style lang="stylus">
  @import './assets/stylus/main'
</style>
