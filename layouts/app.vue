<template>
  <v-app id="example-1">

    <v-toolbar class="white" dark>
      <v-toolbar-side-icon dark @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Project Gato</v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>

    <v-navigation-drawer hide-overlay v-model="drawer" light clipped persistent enable-resize-watcher>
      <v-list dense>
        <template v-for="(item, i) in items">
          <v-layout row v-if="item.heading" align-center :key="i">
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
          </v-layout>
          <v-divider dark v-else-if="item.divider" class="my-4" :key="i"></v-divider>
          <v-list-item :key="i" v-else>
            <v-list-tile>
              <v-list-tile-action>
                <mdi :icon="item.icon"></mdi>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ item.text }}
                </v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer>

    <main>
      <v-navigation-drawer temporary v-model="left"></v-navigation-drawer>
      <v-container fluid>
        <nuxt/>
      </v-container>
      <v-navigation-drawer right temporary v-model="right"></v-navigation-drawer>
    </main>
    <v-footer dark class="white">
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  import Mdi from '../components/Mdi'

  export default {
    components: {
      Mdi
    },
    data() {
      return {
        drawer: true,
        drawerRight: true,
        right: null,
        left: null,
        items: [
          { icon: 'view-dashboard', text: 'Dashboard' },
          { divider: true },
          { heading: 'Admin' },
          { icon: 'account', text: 'Users' },
          { icon: 'domain', text: 'Organizations' },
          { icon: 'account-settings-variant', text: 'Roles' },
          { icon: 'attachment', text: 'Files & Attachments' },
          { icon: 'message-outline', text: 'Notifications' },

          { heading: 'Learning' },
          { icon: 'settings', text: 'Learning Settings' },
          { icon: 'source-fork', text: 'Curriculums' },
          { icon: 'presentation-play', text: 'Courses' },
          { icon: 'calendar', text: 'Sessions' },
          { icon: 'attachment', text: 'Course Materials' },
          { icon: 'school', text: 'Students' },
          { icon: 'map-marker-multiple', text: 'Locations' },
          { icon: 'keyboard', text: 'Approval Requests' },
          { icon: 'certificate', text: 'Certificates' },
          { icon: 'chart-line', text: 'Reports' },

          { heading: 'Site Settings' },
          { icon: 'palette', text: 'Theme Options' },
          { icon: 'key-variant', text: 'Manage License' },
          { icon: 'cart', text: 'E-Commerce' }

        ]
      }
    }
  }
</script>

<style>
  html {
    font-family: "Roboto", "Helvetica Neue", Arial, sans-serif;
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
    margin: 0;
  }

  .button--green {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #3b8070;
    color: #3b8070;
    text-decoration: none;
    padding: 10px 30px;
  }

  .button--green:hover {
    color: #fff;
    background-color: #3b8070;
  }

  .button--grey {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #35495e;
    color: #35495e;
    text-decoration: none;
    padding: 10px 30px;
    margin-left: 15px;
  }

  .button--grey:hover {
    color: #fff;
    background-color: #35495e;
  }
</style>
