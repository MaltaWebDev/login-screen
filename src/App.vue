<template>
  <v-app>
    <v-container fluid>
      <v-row>
        <v-col class="d-flex">
          <v-app-bar class="bg-teal">
            <v-app-bar-nav-icon></v-app-bar-nav-icon>
            <v-spacer></v-spacer>
            <v-tool-bar-title class="mx-auto"
              >Vuetify Dashboard</v-tool-bar-title
            >
            <v-spacer></v-spacer>
            <v-btn variant="elevated" class="mr-2" color="primary">Home</v-btn>
            <v-btn variant="elevated" class="mr-5" color="primary">About</v-btn>
          </v-app-bar>
        </v-col>
      </v-row>
      <v-row class="h-screen">
        <v-col class="d-flex align-center justify-center">
          <v-card width="400" class="mx-auto">
            <v-card-title class="my-5">
              <h1 class="display-1">Login</h1>
            </v-card-title>
            <v-card-text>
              <v-form>
                <v-text-field
                  label="Username"
                  prepend-icon="mdi-account-circle"
                />
                <v-text-field
                  :type="showPassword ? 'text' : 'password'"
                  label="Password"
                  prepend-icon="mdi-lock"
                  :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  @click:append="showPassword = !showPassword"
                />
              </v-form>
            </v-card-text>
            <v-divider></v-divider>
            <v-card-actions>
              <v-btn class="register bg-teal" elevation="2" variant="elevated"
                >Register</v-btn
              >
              <v-spacer></v-spacer>
              <v-btn class="login" color="primary" elevation="2" variant="flat"
                >Login</v-btn
              >
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-footer app class="d-flex flex-column">
            <div class="bg-teal d-flex w-100 align-center px-4">
              <strong>Get connected with us on social networks!</strong>

              <v-spacer></v-spacer>

              <v-btn
                v-for="icon in icons"
                :key="icon"
                class="mx-4"
                :icon="icon"
                variant="plain"
                size="small"
              ></v-btn>
            </div>

            <div class="px-4 py-2 bg-black text-center w-100">
              {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
            </div>
          </v-footer>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    showPassword: false,
  }),
};
</script>

<style>
* {
  caret-color: transparent;
}
</style>
