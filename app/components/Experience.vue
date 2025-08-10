<template>
  <v-card
    id="experience"
    prepend-icon="mdi-folder-multiple"
    variant="flat"
    title="Experience"
    subtitle="This is my work experience information section.">
    <v-timeline
      density="compact"
      side="end"
      v-for="(item, index) in items" :key="index"
    >
      <v-timeline-item
        :class="item.class"
        :dot-color="item.dot_color"
        :size="item.size"
        :fill-dot="item.is_fill_dot"
      >
        <template v-slot:icon>
          <span v-if="item.is_fill_dot">{{ item.fill_dot_title }}</span>
        </template>
        <div class="align-start flex-column">
          <div>
            {{ item.company }}
            <v-chip
              :color="item.company_color"
              :size="item.company_size"
              :label="item.is_company_label"
              
            >
              {{ item.company_duration }}
            </v-chip>
          </div>
          <div>
            {{ item.office_address }}
          </div>
        </div>
      </v-timeline-item>

      <v-timeline-item
        v-for="(posItem, posIndex) in item.positions" :key="posIndex"
        :class="posItem.class"
        :dot-color="posItem.dot_color"
        :size="posItem.size"
        :fill-dot="posItem.is_fill_dot"
      >
        <div class="align-start flex-column">
          <div>
            {{ posItem.position }}
            <v-chip
              :color="posItem.duration_color"
              :size="posItem.duration_size"
              :label="posItem.is_duration_label"
            >
              
              {{ posItem.company_duration }}
            </v-chip>
          </div>
          <div>
            {{ posItem.duration }}
          </div>
          <div>
            {{ posItem.department }}
          </div>
        </div>
      </v-timeline-item>
    </v-timeline>
  </v-card>
</template>
<script setup>
  const items = [
  {
    is_fill_dot: true,
    size: 'large',
    dot_color: 'blue',
    class: 'mb-12',
    fill_dot_title: 'IS',
    company: 'Infosoft Studio under Mini Clean Business Solutions',
    company_duration: '7 years 6 months',
    position: 'Chief Software Architect',
    company_color: 'purple',
    company_size: 'small',
    is_company_label: true,
    office_address: 'Davao, Davao Region, Philippines',
    positions: [
      {
        is_fill_dot: false,
        size: 'x-small',
        dot_color: 'white',
        class: 'mb-12',
        position: 'Chief Software Architect',
        company_duration: '1 year 7 months',
        duration: 'Jan 2024 - Present',
        duration_color: 'purple',
        duration_size: 'small',
        is_duration_label: true,
        department: 'Software Development Team'
      },
      {
        is_fill_dot: false,
        size: 'x-small',
        dot_color: 'white',
        class: 'mb-12',
        position: 'Frontend Web Developer',
        company_duration: '6 years 9 months',
        duration: 'Feb 2018 - Oct 2024',
        duration_color: 'purple',
        duration_size: 'small',
        is_duration_label: true,
        department: 'Software Development Team'
      }
    ]
  },

]
</script>