<template>
  <v-container fluid fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm8 md4>
        <v-card class="elevation-12">
          <v-toolbar dark color="blue">
            <v-toolbar-title>
              Sign Up Form
            </v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form>
              <v-alert :value="true" color="error" icon="warning">
                This user already exists, try a different set of data.
              </v-alert>

              <v-text-field
                prepend-icon="person"
                name="username"
                label="Username"
                :rules="[rules.required]"
              >
              </v-text-field>

              <v-text-field
                prepend-icon="email"
                name="email"
                label="Email"
                :rules="[rules.required, rules.email]"
              >
              </v-text-field>

              <v-text-field
                prepend-icon="lock"
                name="password"
                label="Password"
                type="password"
                v-model="password"
                :rules="[rules.required]"
              >
              </v-text-field>

              <v-text-field
                prepend-icon="lock"
                name="password"
                label="Confirm Password"
                type="password"
                v-model="confirmPassword"
                :rules="[rules.required]"
                :error="!valid()"
              >
              </v-text-field>
            </v-form>
          </v-card-text>
          <v-divider light></v-divider>

          <v-card-actions>
            <v-btn rounded color="black" dark>Sign In</v-btn>
            <v-spacer></v-spacer>
            <v-btn rounded color="success">
              Register
              <v-icon>keyboard_arrow_up</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    password: "",
    confirmPassword: "",
    rules: {
      required: (value) => !!value || "Required",
      email: (value) => {
        const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return pattern.test(value) || "Invalid e-mail.";
      },
    },
  }),
  methods: {
    valid() {
      return this.password === this.confirmPassword;
    },
  },
};
</script>

<style></style>
