<template>
  <v-container class="app-top-bar">
    <v-app-bar color="green darken-3" dense dark>
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

      <v-toolbar-title>Brasileirão 2021 ⚽</v-toolbar-title>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="light-green--text text--lighten-1"
        ><router-link to="/">
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Inicio</v-list-item-title>
          </v-list-item>
          </router-link>

          <router-link to="/classificacao">
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-soccer-field</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Classificação</v-list-item-title>
            </v-list-item>
          </router-link>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-container>
</template>

<script>
export default {
  name: "AppTopBar",
  data() {
    return {
      drawer: false,
      group: null,
    };
  },

};
</script>

<style scoped>

</style>
