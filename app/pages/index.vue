<template>
  <v-container class="fill-height px-2">
    <sharedNavigation :items="items" title="Charmaine Joy P. Rosatace" />

    <v-row justify="center">
     <!--  <v-col cols="8">
        <post />
      </v-col> -->
      <v-col cols="12" sm="11" md="10" lg="8">
        <about />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <skills />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <experience />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <contact />
      </v-col>
    </v-row>
  </v-container>
</template>
<script lang="ts" setup>

  const items = [
  // {
  //   el: '#post',
  //   offset: -70,
  //   icon: 'mdi-post',
  //   title: 'Posts',
  //   model: 'Posts'
  // },
  {
    el: '#about',
    offset: -70,
    icon: 'mdi-account',
    title: 'About Me',
    model: 'About'
  },
  {
    el: '#skill',
    offset: -70,
    icon: 'mdi-tools',
    title: 'Skills',
    model: 'Skills'
  },
  {
    el: '#experience',
    offset: -70,
    icon: 'mdi-folder-multiple',
    title: 'Experience',
    model: 'Experience'
  },
  {
    el: '#contact',
    offset: -70,
    icon: 'mdi-email',
    title: 'Contact Me',
    model: 'Contact Me'
  }]
</script>