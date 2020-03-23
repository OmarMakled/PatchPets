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
          title:
            "PatchPets is looking to hire a new team member who will work for us on a long term basis. An externally contracted employee. We are looking for an individual, not an agency and all work must be performed as an individual. Please confirm that you are applying and will work as an individual and not as part of an agency nor will any outsourcing of the work be performed by anyone but yourself?",
          answer: "Yes",
          check: true
        },
        {
          title:
            "Please confirm your email address which will be used for an invite to a pre-selection technical interview.",
          answer: "omar.makled@gmail.com"
        },
        {
          title:
            "Do you have at least four years of commercial experience with HTML?",
          answer: "Yes",
          check: true
        },
        {
          title:
            "Do you have at least four years of commercial experience with CSS?",
          answer: "Yes",
          check: true
        },
        {
          title:
            "Do you have at least four years of commercial experience with JavaScript?",
          answer: "let Yes;)",
          check: true
        },
        {
          title:
            "Do you have at least four years of commercial experience with PHP?",
          answer: "Yes",
          check: true
        },
        {
          title:
            "Do you have at least four years of commercial experience with MySQL (or an equivalent SQL service to MySQL)?",
          answer: "Yes",
          check: true,
          note: "+ ES, MongoDB"
        },
        {
          title:
            "Do you have any commercial experience in DevOps and if so how many years at a commercial level?",
          answer: "Yes",
          check: true,
          note: "1 year"
        },
        {
          title:
            "Are you comfortable using Linux servers on a daily basis and if yes, to what level of experience?",
          answer: "Yes",
          check: true,
          progress: {
            value: 45,
            max: 100
          }
        },
        {
          title:
            "Do you have any experience with GraphQL and if yes, to what level of experience?",
          answer: "Yes",
          check: true,
          progress: {
            value: 20,
            max: 100
          }
        },
        {
          title:
            "Do you have any experience with Laraval and if yes, to what level of experience?",
          answer: "Yes",
          check: true,
          progress: {
            value: 90,
            max: 100
          }
        },
        {
          title:
            "Do you have any experience with designing and developing APIs and if yes, to what level of experience and in what languages?",
          answer: "Yes",
          note: "(Express) Node.js, Lumen (PHP)",
          check: true,
          progress: {
            value: 80,
            max: 100
          }
        },
        {
          title:
            "Do you have any experience optimising your code and other team members code to maintain high-security standards and to optimise the code for speed and efficiency and if yes, to what level of experience?",
          answer: "Yes",
          note: "2 years working with agile & cross functional team",
          check: true,
          progress: {
            value: 70,
            max: 100
          }
        },
        {
          title:
            "Do you have any commercial experience with Python and if yes, to what level of experience?",
          answer: "No",
          check: false
        },
        {
          title:
            "Do you have any commercial experience with Redis and if yes, to what level of experience?",
          answer: "Yes",
          check: true
        },
        {
          title:
            "Do you have any commercial experience with Angular and if yes, to what level of experience?",
          answer: "Yes",
          note: "AngularJS, Angular2, Angular4 then fall in love Vue.js",
          check: true,
          progress: {
            value: 80,
            max: 100
          }
        },
        {
          title:
            "How many commercial years experience do you have working with services and infrastructure with PAAS and IAAS, for projects?",
          answer: "1 year",
          note: "Own projects, but I used to have a DevOps"
        },
        {
          title:
            "Are you prepared to work in an agile development team environment with multiple other developers taking direction from a team leader and senior lead developer?",
          check: true,
          answer: "Yup",
          icon: "music-note-list"
        },
        {
          title:
            "Are you willing to participate and contribute to regular weekday developer meetings (similar to scrum meetings)?",
          check: true,
          answer: "Yup",
          icon: "music-note-list"
        },
        {
          title:
            "Are you prepared to sign an NDA (non-disclosure agreement) before the commencement of work?",
          check: true,
          answer: "Yes"
        },
        {
          title:
            "Could you confirm what city and timezone you are located in? Please provide in the format of [City name] [timezone offset]",
          answer: "Cairo UTC+02:00"
        },
        {
          title:
            "Do you have a suitable fast Internet connection for regular development work?",
          check: true,
          answer: "Yes"
        },
        {
          title:
            "Is your work environment quiet i.e. no noisy background noises that will be distracting to other team members on the call?",
          check: true,
          answer: "Yes",
          note: "close to main street so sometimes noisy comes"
        },
        {
          title:
            "Can you confirm your availability to work full-time a regular 40 hours a week during weekdays?",
          check: true,
          answer: "Yes"
        },
        {
          title:
            "Do you envisage that there will be any other priorities or projects that will interfere with your regular full-time weekday working hours for Patchpets?",
          check: false,
          answer: "No",
          note: "Study and practice some new topics"
        },
        {
          title:
            "PatchPets takes hiring and access to customer data very seriously. If your application is successful, are you willing to undergo a police security check prior to starting the role?",
          check: true,
          answer: "Yes"
        },
        {
          title:
            "Please send through a voice recording with a brief introduction to yourself.",
          answer: "sent"
        }
      ]
    };
  }
};
</script>
