<template>
  <v-container fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm8 md4>
        <v-card class="elevation-12">
          <v-toolbar dark color="blue">
            <v-toolbar-title>
              Login Form
            </v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-text-field
              prepend-icon="person"
              name="email"
              label="Email"
              type="email"
            >
            </v-text-field>
            <v-text-field
              prepend-icon="lock"
              name="password"
              label="Password"
              type="password"
            >
            </v-text-field>
          </v-card-text>
          <v-divider light></v-divider>
          <v-card-actions>
            <v-btn rounded color="indigo" dark>
              Sign In
            </v-btn>
            <v-spacer></v-spacer>
            <v-btn rounded color="primary" dark>
              Login
              <v-icon>keyboard_arrow_right</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "Login",
};
</script>

<style></style>
