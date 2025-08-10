<template>
  <v-card 
    id="contact"
    prepend-icon="mdi-email"
    variant="flat"
    title="Contact Me"
    subtitle="This is my contact information section.">

    <v-list
      v-for="(item, index) in items":key="index">
      <v-list-item prepend-icon="mdi-phone">
        <v-list-item-title>{{ item.contact_no }}</v-list-item-title>
      </v-list-item>

      <v-list-item prepend-icon="mdi-email">
        <v-list-item-title>{{ item.email_address }}</v-list-item-title>
      </v-list-item>

      <v-list-item prepend-icon="mdi-map-marker">
        <v-list-item-title>{{ item.home_address }}</v-list-item-title>
      </v-list-item>
    </v-list>

    <v-row justify="left" class="mx-3">
      <v-col xs="1" sm="2" md="2" lg="2"
        v-for="(arrList, arrListIndex) in arraylist":key="arrListIndex">
        <v-btn icon :color="arrList.color" :href="arrList.link" target="_blank" rel="noopener noreferrer">
        <v-icon>{{ arrList.icon }}</v-icon>
      </v-btn>
      </v-col>
    </v-row>
  </v-card>
</template>
<script setup>
  const items = [
    {
      contact_no: '+63 995 1872 924',
      email_address: 'iamcjrosatace@gmail.com',
      home_address: 'Bato Sta. Cruz, Davao Del Sur'
    }
  ]
  const arraylist = [{
    name: 'Facebook',
    link: 'https://www.facebook.com/cjrosatace',
    icon: 'mdi-facebook',
    color: 'blue'
  },
  {
    name: 'LinkedIn',
    link: 'https://www.linkedin.com/in/charmaine-joy-rosatace-397808105/',
    icon: 'mdi-linkedin',
    color: 'blue'
  },
  {
    name: 'Lichess',
    link: 'https://lichess.org/@/Cj_17',
    icon: 'mdi-chess-knight',
    color: 'black'
  }
]
</script>