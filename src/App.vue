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
      <p class="text-black-50">
        <span v-if="question.type == 'skills'">-</span>
        <span v-else>{{++index}})</span>
        {{question.title}}
      </p>
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
          title: "Your price per hour in $",
          answer: "$25"
        },
        {
          title: "Your availability per week in h",
          answer: "40h"
        },
        {
          title:
            "We suggest sending a short video presenting yourself, so we can test your level of English. In case you can not make it we will need to have a skype call for that. Here is an app to use for recording: https://www.screencastify.com/",
          answer: "https://vimeo.com/305335935"
        },
        {
          title: "Your CV",
          answer:
            "https://docs.google.com/document/d/1RPcLKZmQAkFeFrL6avrUo-Y8-KFobKdUkyzSLH-ghTA/edit?usp=sharing"
        },
        {
          title:
            "Years of Betting/Sports coding. Examples of projects you did in this industry",
          answer: "No",
          check: false
        },
        {
          title:
            "What is your experience with each: .Please take some time to browse all of the skills below and rate yourself honestly on a scale of 1 to 5 (1 = Beginner, 2 = Familiar, 3 = Proficient, 4 = Expert, 5 = Master)"
        },
        {
          title: "PHP 7",
          note: "5",
          type: "skills",
          progress: {
            value: 5,
            max: 5
          }
        },
        {
          title: "Symfony framework (3/4)",
          note: "4",
          type: "skills",
          progress: {
            value: 4,
            max: 5
          }
        },
        {
          title: "Redis",
          type: "skills",
          note: "3",
          progress: {
            value: 3,
            max: 5
          }
        },
        {
          title: "RabbitMQ",
          type: "skills",
          note: "3",
          progress: {
            value: 3,
            max: 5
          }
        },
        {
          title: "Git (GitFlow)",
          type: "skills",
          note: "5",
          progress: {
            value: 5,
            max: 5
          }
        },
        {
          title: "Jenkins",
          type: "skills",
          note: "1",
          progress: {
            value: 1,
            max: 5
          }
        },
        {
          title: "Beanstalk",
          type: "skills",
          note: "1",
          progress: {
            value: 1,
            max: 5
          }
        },
        {
          title: "Capistrano",
          type: "skills",
          note: "1",
          progress: {
            value: 1,
            max: 5
          }
        },
        {
          title: "Linux",
          type: "skills",
          note: "3",
          progress: {
            value: 3,
            max: 5
          }
        },
        {
          title: "Node.JS",
          type: "skills",
          note: "4",
          progress: {
            value: 4,
            max: 5
          }
        },
        {
          title: "Experience in Betting industry",
          type: "skills",
          note: "0",
          progress: {
            value: 0,
            max: 5
          }
        }
      ]
    };
  }
};
</script>
