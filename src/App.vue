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
      <div>
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
        <ul v-if="question.links">
          <li v-for="(link, index) in question.links" :key="index">
            <a :href="link">{{link}}</a>
          </li>
        </ul>
      </div>
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
          title: `Prefers to take advantage of Eloquent and Laravel's other magic methods instead of relying on raw DB/PHP queries`,
          check: true
        },
        {
          title: "You have excellent PHP skills, using the latest OOP features",
          check: true
        },
        {
          title: `You love testing, TDD, continuous integration and deployment and can’t imagine coding any other way (or you’d love to learn). PHPUnit is your friend!`,
          check: true
        },
        {
          title: `Skill and a passion for system administration (unix/linux), continuous integration & deployment and cloud management tools will be highly regarded`,
          check: true
        },
        {
          title: `You're a strong team player, you’re keen to have your voice heard while appreciating the opinions of others`,
          check: true
        },
        {
          title: `You’re organized and methodical, with experience working in an Agile team environment`,
          check: true
        },
        {
          title: `At least 2 years dealing with PHP. Knowledge and practical experience with PHP`,
          check: true
        },
        {
          title: "Know Jquery, Ajax, JavaScript",
          check: true
        },
        {
          title: "Strong knowing of OOP and patterns",
          check: true
        },
        {
          title: `You must know how to deal with PDO and Doctrine ORM(or similar).`,
          check: true
        },
        {
          title: `Experience in plain SQL.`,
          check: true
        },
        {
          title: `Knowing Laravel framework`,
          check: true
        },
        {
          title: `You must use git`,
          check: true
        },
        {
          title: `HTML5, CSS3 (bootstrap).`,
          check: true
        },
        {
          title: `Understand and support legacy code`,
          check: true
        },
        {
          title: ` Deal with nginx and know how setup you server.`,
          check: true
        },
        {
          title: `Work in a team.`,
          check: true
        },
        {
          title: `Examples`,
          links: [
            "https://aqarmap.com.eg/en/",
            "https://safebid.xyz/",
            "http://baytlibya.com/",
            "http://157.230.22.211:8088/",
            "https://vimeo.com/305335935",
            "http://omarmakled.me/"
          ]
        },
        {
          title:
            "It would also be great to know how long it took for you to complete the sample projects to get an idea of your speed of deployment",
          answer: `Let's talk `
        }
      ]
    };
  }
};
</script>
