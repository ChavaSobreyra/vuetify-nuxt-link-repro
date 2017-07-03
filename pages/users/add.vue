<style scoped>
  h1 {
    font-size: 28px;
    font-weight: 500;
  }
</style>


<template>
  <div>
    <v-layout row>
      <v-flex xs10 offset-xs1>

        <v-card>
          <v-card-text>
            <h1 class="mt-2 mb-4">Add User</h1>
            <v-divider></v-divider>
            <v-avatar class="my-4">
              <img src="https://s3.amazonaws.com/uifaces/faces/twitter/aiiaiiaii/128.jpg">
            </v-avatar>
            <v-card-row class="mt-4">
              <v-flex xs12 sm4>
                <v-text-field name="firstName" label="First Name" v-model="firstName" id="firstName"></v-text-field>
              </v-flex>
              <v-flex xs12 sm4>
                <v-text-field name="lastName" label="Last Name" v-model="lastName" id="lastName"></v-text-field>
              </v-flex>
              <v-flex xs12 sm4>
                <v-text-field name="email" label="Email" v-model="email" id="email"></v-text-field>
              </v-flex>
            </v-card-row>
            <v-card-row class="mt-4">
              <v-flex xs12 sm4>
                <v-text-field name="phone" label="Phone Number" v-model="phone" id="phone"></v-text-field>
              </v-flex>
              <v-flex xs12 sm4>
                <v-select v-bind:items="roles" v-model="role" label="Role" dark single-line auto></v-select>
              </v-flex>
              <v-flex xs12 sm4>
                <v-select v-bind:items="languages" v-model="language" label="Preferred Language" dark single-line auto></v-select>
              </v-flex>
            </v-card-row>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>


<script>
  export default {
    data() {
      return {
        firstName: '',
        lastName: '',
        email: '',
        phone: '',
        role: '',
        language: '',

        roles: [
          'Super Admin', 'Organization Admin', 'Instructor', 'Reporter'
        ],
        languages: [
          'English', 'French', 'German', 'Spanish'
        ]
      }
    }
  }
</script>
