<template>
  <v-card
    id="skill"
    prepend-icon="mdi-tools"
    variant="flat"
    title="Skills"
    subtitle="This is my personal skills information section."
    class="px-2">
    <v-row wrap>
      <v-col xs="12" sm="12" md="6">
        <div :class="smAndUp ? sm-and-up-container : 'xs-container'">
          <ClientOnly>
            <SharedBarChart :chartData="data" :chartOptions="options" />
            <template #fallback>
              <p>Loading chart...</p>
            </template>
          </ClientOnly>
        </div>
      </v-col>
      <v-col xs="12" sm="12" md="6">
        <div :class="smAndUp ? sm-and-up-container : 'xs-container'">
          <ClientOnly>
            <SharedBarChart :chartData="gitData" :chartOptions="gitOptions" />
            <template #fallback>
              <p>Loading chart...</p>
            </template>
          </ClientOnly>
        </div>
      </v-col>
      <v-col xs="12" sm="12" md="6">
        <div :class="smAndUp ? sm-and-up-container : 'xs-container'">
          <ClientOnly>
            <SharedBarChart :chartData="frameworksData" :chartOptions="frameworksOptions" />
            <template #fallback>
              <p>Loading chart...</p>
            </template>
          </ClientOnly>
        </div>
      </v-col>
      <v-col xs="12" sm="12" md="6">
        <div :class="smAndUp ? sm-and-up-container : 'xs-container'">
          <ClientOnly>
            <SharedBarChart :chartData="backFrameworksData" :chartOptions="backFrameworksOptions" />
            <template #fallback>
              <p>Loading chart...</p>
            </template>
          </ClientOnly>
        </div>
      </v-col>
      <v-col cols="12" xs="12" sm="12" md="6">
        <div :class="smAndUp ? sm-and-up-container : 'xs-container'">
          <ClientOnly>
            <SharedBarChart :chartData="devopsData" :chartOptions="devopsOptions" />
            <template #fallback>
              <p>Loading chart...</p>
            </template>
          </ClientOnly>
        </div>
      </v-col>
    </v-row>
  </v-card>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { useDisplay } from 'vuetify'

const { smAndUp } = useDisplay()

// HTML, CSS, and JavaScript Skillset Overview
const data = ref({
  labels: ['CSS Grid & Flexbox', 'HTML5 & Semantic Markup', 'JavaScript', 'Ecmascript', 'Typescript'],
  datasets: [
    {
      label: 'Proficiency',
      backgroundColor: [
        'rgba(255, 99, 132, 0.2)',
        'rgba(255, 159, 64, 0.2)',
        'rgba(255, 205, 86, 0.2)',
        'rgba(75, 192, 192, 0.2)',
        'rgba(54, 162, 235, 0.2)',
        'rgba(153, 102, 255, 0.2)',
        'rgba(201, 203, 207, 0.2)'
      ],
      borderColor: [
        'rgb(255, 99, 132)',
        'rgb(255, 159, 64)',
        'rgb(255, 205, 86)',
        'rgb(75, 192, 192)',
        'rgb(54, 162, 235)',
        'rgb(153, 102, 255)',
        'rgb(201, 203, 207)'
      ],
      data: [90, 93, 95, 90, 40],
    }
  ]
});
// Define your chart options
const options = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    title: {
      display: true,
      text: 'HTML, CSS, and JavaScript Skillset Overview',
    },
  },
  scales: {
    y: {
      stacked: true,
      beginAtZero: true
    },
    x: {
      stacked: true
    }
  }
});


// HTML, CSS, and JavaScript Skillset Overview
const gitData = ref({
  labels: ['GIT Commands', 'Platform built on Git: Bibucket', 'Platform built on Git: Github'],
  datasets: [
    {
      label: 'Proficiency',
      backgroundColor: [
        'rgba(255, 99, 132, 0.2)',
        'rgba(255, 159, 64, 0.2)',
        'rgba(255, 205, 86, 0.2)',
        'rgba(75, 192, 192, 0.2)',
        'rgba(54, 162, 235, 0.2)',
        'rgba(153, 102, 255, 0.2)',
        'rgba(201, 203, 207, 0.2)'
      ],
      borderColor: [
        'rgb(255, 99, 132)',
        'rgb(255, 159, 64)',
        'rgb(255, 205, 86)',
        'rgb(75, 192, 192)',
        'rgb(54, 162, 235)',
        'rgb(153, 102, 255)',
        'rgb(201, 203, 207)'
      ],
      data: [96, 98, 70],
    }
  ]
});

// Define your chart options
const gitOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    title: {
      display: true,
      text: 'Version Control with Git Skillset Overview',
    },
  },
  scales: {
    y: {
      stacked: true,
      beginAtZero: true
    },
    x: {
      stacked: true
    }
  }
});

// Frontend Frameworks & Component Frameworks Skillset Overview
const frameworksData = ref({
  labels: ['Vuejs 1, 2 & 3', 'Nuxt 2 & 3', 'Vuetify 1,2 & 3', 'GraphQL', 'Bootstrap','React', 'Svelte'],
  datasets: [
    {
      label: 'Proficiency',
      backgroundColor: [
        'rgba(255, 99, 132, 0.2)',
        'rgba(255, 159, 64, 0.2)',
        'rgba(255, 205, 86, 0.2)',
        'rgba(75, 192, 192, 0.2)',
        'rgba(54, 162, 235, 0.2)',
        'rgba(153, 102, 255, 0.2)',
        'rgba(201, 203, 207, 0.2)'
      ],
      borderColor: [
        'rgb(255, 99, 132)',
        'rgb(255, 159, 64)',
        'rgb(255, 205, 86)',
        'rgb(75, 192, 192)',
        'rgb(54, 162, 235)',
        'rgb(153, 102, 255)',
        'rgb(201, 203, 207)'
      ],
      data: [90, 89, 90, 45, 30, 20, 10]
    }
  ]
});

// Define your chart options
const frameworksOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    title: {
      display: true,
      text: 'Frontend & Component Frameworks Skillset Overview',
      font: {
        size: 12
      },
      padding: {top: 10, left: 10, right: 10, bottom: 0}
    },
  },
  scales: {
    y: {
      stacked: true,
      beginAtZero: true
    },
    x: {
      stacked: true
    }
  }
});

// Back-End Development Skillset Overview
const backFrameworksData = ref({
  labels: ['PHP','Node.js', 'SQL (MySQL, PostgreSQL)', 'GraphQL', 'Laravel'],
  datasets: [
    {
      label: 'Proficiency',
      backgroundColor: [
        'rgba(255, 99, 132, 0.2)',
        'rgba(255, 159, 64, 0.2)',
        'rgba(255, 205, 86, 0.2)',
        'rgba(75, 192, 192, 0.2)',
        'rgba(54, 162, 235, 0.2)',
        'rgba(153, 102, 255, 0.2)',
        'rgba(201, 203, 207, 0.2)'
      ],
      borderColor: [
        'rgb(255, 99, 132)',
        'rgb(255, 159, 64)',
        'rgb(255, 205, 86)',
        'rgb(75, 192, 192)',
        'rgb(54, 162, 235)',
        'rgb(153, 102, 255)',
        'rgb(201, 203, 207)'
      ],
      data: [30, 10, 25, 20, 15],
    }
  ]
});

// Define your chart options
const backFrameworksOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    title: {
      display: true,
      text: 'Back-End Development & Frameworks Skillset Overview',
      font: {
        size: 12
      },
      padding: {top: 10, left: 10, right: 10, bottom: 0}
    },
  },
  scales: {
    y: {
      stacked: true,
      beginAtZero: true
    },
    x: {
      stacked: true
    }
  }
});

// DevOps and Cloud Computing Skillset Overview
const devopsData = ref({
  labels: ['SSH', 'Google Cloud', 'Dockerized Nginx'],
  datasets: [
    {
      label: 'Proficiency',
      backgroundColor: [
        'rgba(255, 99, 132, 0.2)',
        'rgba(255, 159, 64, 0.2)',
        'rgba(255, 205, 86, 0.2)',
        'rgba(75, 192, 192, 0.2)',
        'rgba(54, 162, 235, 0.2)',
        'rgba(153, 102, 255, 0.2)',
        'rgba(201, 203, 207, 0.2)'
      ],
      borderColor: [
        'rgb(255, 99, 132)',
        'rgb(255, 159, 64)',
        'rgb(255, 205, 86)',
        'rgb(75, 192, 192)',
        'rgb(54, 162, 235)',
        'rgb(153, 102, 255)',
        'rgb(201, 203, 207)'
      ],
      data: [40, 20, 40],
    }
  ]
});

// Define your chart options
const devopsOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    title: {
      display: true,
      text: 'DevOps and Cloud Computing Skillset Overview',
    },
  },
  scales: {
    y: {
      stacked: true,
      beginAtZero: true
    },
    x: {
      stacked: true
    }
  }
});
</script>

<style scoped>
.xs-container {
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
  border-radius: 8px;
  height: 350px; /* Give the chart container a fixed height or min-height */
}
.sm-and-up-container {
  max-width: 800px;
  margin: 20px auto;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
  border-radius: 8px;
  height: 350px; /* Give the chart container a fixed height or min-height */
}
</style>