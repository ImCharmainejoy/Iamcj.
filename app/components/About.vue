<template>
  <v-card
    id="about"
    prepend-icon="mdi-account"
    variant="flat"
    title="About Me"
    subtitle="This is my personal information section."
  >
    <template v-slot:prepend>
      <v-icon size="x-large"></v-icon>
    </template>

    <v-list-item
      v-for="(item, index) in items":key="index">

      <v-list-item-title>
        <v-icon>mdi-rename-box-outline</v-icon> {{ item.label }}: {{ item.value }}
      </v-list-item-title>

      <v-row>
        <v-col cols="12"
          v-if="item.chips">
          <v-chip-group class="mt-0" column>
            <v-chip
              class="text-black pa-2"
              v-for="(chipVal, chipIndex) in item.chips":key="chipIndex"
            >{{ chipVal }}</v-chip>
          </v-chip-group>
        </v-col>
        <v-col cols="12" sm="11" md="10" lg="8"
          v-if="item.progress">
          <v-card-text>
            <v-list>
              <v-list-item
               v-for="(val, valIndex) in item.progress":key="valIndex">
                <v-list-item-title class="font-weight-medium">{{ val.name }}</v-list-item-title>
                <v-list-item-subtitle>{{ val.description }}</v-list-item-subtitle>
                <template v-slot:append>
                  <v-icon :color="val.status_color"> {{ val.icon_status }}</v-icon>
                </template>
              </v-list-item>
              </v-list>
          </v-card-text>
        </v-col>
        <v-col cols="6"
          v-if="item.links"
          v-for="(valLink, valLinkIndex) in item.links":key="valLinkIndex">
          <v-card
            append-icon="mdi-open-in-new"
            class="mx-auto"
            :style="{ color: valLink.color }"
            :href="valLink.link"
            max-width="344"
            :prepend-icon="valLink.icon"
            rel="noopener"
            subtitle="Check out the official account"
            target="_blank"
            :title="valLink.name"
          ></v-card>
        </v-col>
        <v-col cols="12" sm="11"
          v-if="item.arraylist">
          <v-list lines="three" class="py-0">
            <v-list-item
              v-for="(edu, arrListIndex) in item.arraylist"
              :key="arrListIndex"
              class="mb-4"
            >
              <template v-slot:prepend>
                <v-avatar color="primary-lighten-2" size="48">
                  <v-icon color="white">mdi-school</v-icon>
                </v-avatar>
              </template>

              <v-list-item-title class="font-weight-medium text-body-1">
                {{ edu.degree }}
              </v-list-item-title>
              <v-list-item-subtitle class="text-grey-darken-1">
                {{ edu.institution }} &bull; {{ edu.location }}
                <br>
                {{ edu.startDate }} - {{ edu.endDate }}
              </v-list-item-subtitle>

              <template v-slot:append v-if="edu.gpa">
                <v-chip color="info" label size="small">GPA: {{ edu.gpa }}</v-chip>
              </template>

              <v-list-item-action v-if="edu.honors || edu.notes">
                <div class="mt-2 text-caption">
                  <div v-if="edu.honors" class="text-purple-darken-1">
                    <v-icon size="small" start>mdi-trophy</v-icon>
                    {{ edu.honors }}
                  </div>
                  <div v-if="edu.notes">{{ edu.notes }}</div>
                </div>
              </v-list-item-action>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
    </v-list-item>
  </v-card>
</template>
<script setup>
  import myAvatar from '@/assets/images/disneyme.png'

  const items = [
    {
      label: 'Languages I Speak',
      value: '',
      progress: [{
        name: 'Cebuano',
        description: 'Native / Bilingual proficiency',
        status_color: 'success',
        icon_status: 'mdi-check-circle'
      },
      {
        name: 'Filipino (Tagalog)',
        description: 'Native / Bilingual proficiency',
        status_color: 'success',
        icon_status: 'mdi-check-circle'
      },
      {
        name: 'English',
        description: 'Conversational proficiency',
        status_color: 'info',
        icon_status: 'mdi-information'
      },
      {
        name: 'Japanese',
        description: 'Basic proficiency (N5)',
        status_color: 'warning',
        icon_status: 'mdi-alert-circle'
      },
      {
        name: 'Korean',
        description: 'Basic proficiency',
        status_color: 'warning',
        icon_status: 'mdi-alert-circle'
      }]
    },
    {
      label: 'Hobbies',
      value: '',
      chips: ['🎏 Playing Chess', '🎥 Watching Medical/Sports/Fantasy Movies', '💖 Exercise', '🌲 Camping', '🎵 Listening to Music']
    },
    {
      label: 'Educational Background',
      value: '',
      arraylist: [
        {
          degree: 'Bachelor of Science in Computer Science',
          institution: 'Cor Jesu College',
          location: 'Digos City, Philippines',
          startDate: 'June 2011',
          endDate: 'April 2016',
          gpa: '1.9/3.0',
          honors: 'Annual Awardee & Chess Varsity'
        },
        {
          degree: 'High School',
          institution: 'Digos City National High School',
          location: 'Digos City, Philippines',
          startDate: 'June 2007',
          endDate: 'April 2011',
          honors: 'Chess Varsity'
        },
        {
          degree: 'Elementary School',
          institution: 'Apolinar Franco Sr. Elementary School',
          location: 'Bato Sta. Cruz Davao Del Sur, Philippines',
          startDate: 'June 2003',
          endDate: 'April 2007',
          honors: 'With Merit & Chess Player'
        }
      ]
    }
  ]
</script>
<style scoped>
.negative-top {
  margin-top: -10px
}
</style>
