<template>
  <div class="container p-4" id="app">
    <h6 class="mb-4">
      Build with
      <b-icon icon="heart-fill" variant="danger" class="ml-1 mr-1"></b-icon>using
      <b-badge variant="light mr-2">Docker</b-badge>
      <b-badge variant="light mr-2">Digitalocean</b-badge>
      <b-badge variant="light mr-2">Nginx</b-badge>
      <b-badge variant="light mr-2">Vue.js</b-badge>
      <b-badge variant="light mr-2">Bootstrap</b-badge>
      <b-badge variant="light mr-2">HTML</b-badge>
    </h6>
    <div v-for="(question, index) in questions" :key="index" class="border-bottom mb-3">
      <p class="text-black-50">{{++index}}) {{question.title}}</p>
      <audio v-if="question.audio" controls>
        <source :src="question.src" type="audio/x-m4a" />
      </audio>
      <p>
        <b-icon v-if="question.check === true" icon="check"></b-icon>
        <b-icon v-if="question.check === false" icon="x"></b-icon>
        {{question.answer}}
        <b-icon v-if="question.icon" :icon="question.icon"></b-icon>
        <b-progress
          v-if="question.progress"
          :value="question.progress.value"
          :max="question.progress.max"
          animated
        ></b-progress>
        <span class="badge bg-info text-white" v-if="question.note">{{question.note}}</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data: () => {
    return {
      questions: [
        {
          title: "Vuejs",
          answer: "+3 Years",
          progress: {
            value: 90,
            max: 100
          }
        },
        {
          title: "laravel",
          answer: "+5 Years",
          progress: {
            value: 90,
            max: 100
          }
        },
        {
          title: "JavaScript",
          answer: "+5 Years",
          progress: {
            value: 80,
            max: 100
          }
        },
        {
          title: "MySql",
          answer: "+5 Years",
          progress: {
            value: 80,
            max: 100
          }
        },
        {
          title: "Rest API",
          answer: "+3 Years",
          progress: {
            value: 80,
            max: 100
          }
        },
        {
          title: "Git",
          answer: "+5 Years",
          progress: {
            value: 80,
            max: 100
          }
        },
        {
          title: "Bootstrap",
          answer: "+5 Years",
          progress: {
            value: 90,
            max: 100
          }
        },
        {
          title: "http://omarmakled.me/",
          src: "omar.m4a",
          audio: true
        },
        {
          title: "Screencasts",
          answer: "https://vimeo.com/305335935"
        }
      ]
    };
  }
};
</script>
