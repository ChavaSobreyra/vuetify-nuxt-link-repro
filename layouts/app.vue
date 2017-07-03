<template>
  <v-app id="example-1">

    <v-toolbar class="white" dark>
      <v-toolbar-side-icon dark @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Project Gato</v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>

    <v-navigation-drawer hide-overlay v-model="drawer" light clipped persistent disable-route-watcher>
      <v-list dense>
        <nuxt-link to="/users">
          Normal nuxt-link to /users
        </nuxt-link>
        <br>
        <br>
        <nuxt-link to="/users/add">
          Normal nuxt-link to /users/add
        </nuxt-link>

        <v-list-item>
          <v-list-tile href="/users" nuxt ripple>
            <v-list-tile-action>
              <mdi icon="account"></mdi>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                Users
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list-item>

        <v-list-item>
          <v-list-tile href="/users/add" nuxt ripple>
            <v-list-tile-action>
              <mdi icon="account"></mdi>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                Users Add
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>

    <main>
      <v-navigation-drawer temporary v-model="left"></v-navigation-drawer>
      <v-container fluid>
        <nuxt></nuxt>
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
          { icon: 'view-dashboard', text: 'Dashboard', link: '/users/add' },
          { icon: 'account', text: 'Users', link: '/users' }
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

  .toolbar {
    z-index: 6;
  }
</style>
