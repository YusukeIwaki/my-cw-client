<template>
  <v-app>
    <v-toolbar dark color="primary" app>
      <v-toolbar-title>仕事を探す</v-toolbar-title>
      <v-spacer />
      <v-btn to="/query" icon>
        <v-icon>search</v-icon>
      </v-btn>
    </v-toolbar>
    <v-content app>
      <v-container>
        <router-link to="/about">About</router-link>
        これはHome
      </v-container>
    </v-content>
  </v-app>
</template>