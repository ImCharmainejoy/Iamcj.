<template>
  <v-row justify="center">
    <v-col cols="12" v-for="(item, index) in items" :key="index">
      <v-card
        id="post"
        color="surface-variant"
        prepend-icon="mdi-linkedin"
        variant="outlined"
        title="LinkedIn"
      >
        <template v-slot:prepend>
          <v-icon size="x-large"></v-icon>
        </template>

        <v-card-text class="text-h5 py-2">
          
          {{ item.post }}
        </v-card-text>

        <v-card-actions>
          <v-list-item class="w-100">
            <template v-slot:prepend>
              <v-avatar
                color="grey-darken-3"
                :image="myAvatar"
              ></v-avatar>
            </template>

            <v-list-item-title>Cj Rosatace</v-list-item-title>

            <v-list-item-subtitle>{{ item.position }}</v-list-item-subtitle>

            <template v-slot:append>
              <div class="justify-self-end">
                <v-icon class="me-1" icon="mdi-heart" color="red"></v-icon>
                <span class="subheading me-2">{{ item.reaction }}</span>
                <span class="me-1">·</span>
                <v-icon class="me-1" icon="mdi-share-variant" color="blue"></v-icon>
                <span class="subheading">{{ item.share }}</span>
              </div>
            </template>
          </v-list-item>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>
<script setup>
  import myAvatar from '@/assets/images/disneyme.png'

  const items = [{
    post: 'ViteConf 2025: First time In-person in amsterdam on Oct. 9-10, 2025',
    reaction: 517,
    share: 6242,
    position: 'Chief Software Architect'
  },
  {
    post: 'FRONTEND NATION 2024: The largest free online frontend event. ever.',
    reaction: '3.5M',
    share: '400K',
    position: 'Software Developer'
  },
  {
    post: 'VueConf US 2019: Evan You is the creator of Vue.js. In his State of Vuenation talk, he will cover what has been happening with Vue.js in the last few months, growth that has taken place, and exciting new things to look forward to.',
    reaction: '2.3M',
    share: '100K',
    position: 'Software Developer'
  },
  {
    post: `Why Vue js ? It's easy to learn. According to https://naturaily.com/blog/vue-js-2018 In 2018, the VueJS project has surpassed Facebook's React in terms of popularity on GitHub.`,
    reaction: '1.6M',
    share: '64k',
    position: 'Software Developer'
  }]
</script>
<style scoped>
.negative-top {
  margin-top: -10px
}
</style>
