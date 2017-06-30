<template>
  <div>
    <v-container>
      <v-layout row>
        <v-flex xs12 md6 offset-md3 lg4 offset-lg4>
          <div class="text-xs-center mt-5 mb-5">
            <img class="logo" src="/images/pg-logo.png">
          </div>
          <v-text-field name="username" label="Username" v-model="username" id="username"></v-text-field>
          <v-text-field name="password" label="Password" v-model="password" id="password" :append-icon="hidden ? 'visibility' : 'visibility_off'" :append-icon-cb="() => (hidden = !hidden)" :type="hidden ? 'password' : 'text'">
          </v-text-field>

          <v-btn light default block class="primary">Sign In</v-btn>
        </v-flex>
      </v-layout>

    </v-container>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        hidden: true,
        password: '',
        username: ''
      }
    }
  }
</script>

<style scoped>
  .logo {
    width: 100%;
  }
</style>
