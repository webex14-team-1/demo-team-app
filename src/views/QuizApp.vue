<template>
  <h1>Vue クイズ</h1>
  <div class="app">
    <h2>Q. {{ quiz.text }}</h2>
    <img class="quiz-image" v-bind:src="imagepath" alt="沖縄クイズ" />

    <div class="container">
      <button v-on:click="choice(0)">
        {{ quiz.choices[0].text }}
      </button>
      <button v-on:click="choice(1)">
        {{ quiz.choices[1].text }}
      </button>
      <button v-on:click="choice(2)">
        {{ quiz.choices[2].text }}
      </button>
    </div>
    <div>{{ feedback }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      imagepath: require("@/views/images/okinawa.jpeg"),

      feedback: "",
      quiz: {
        text: "沖縄から持ち出し禁止ものもは？",
        Image: " @/views/images/satsumaimo.jpg",
        choices: [
          {
            text: "サツマイモ",
            isCorrect: true,
            feedback:
              "正解！沖縄のサツマイモに寄生する害虫を本土に持ち込まないようにするため！",
          },
          {
            text: "パイナップル",
            isCorrect: false,
            feedback: "残念！沖縄県はパイナップルの生産量が日本１！",
          },
          {
            text: "サトウキビ",
            isCorrect: false,
            feedback: "残念！沖縄のサトウキビの全国シェアは60％！",
          },
        ],
      },
    }
  },
  methods: {
    choice(i) {
      this.feedback = this.quiz.choices[i].feedback
      // 正解のボタンを押したときに沖縄の写真をサツマイモの写真に変える
      if (this.quiz.choices[i].isCorrect === true) {
        this.imagepath = require("@/views/images/satsumaimo.jpg")
      }
    },
  },
}
</script>

<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

.quiz-image {
  height: 300px;
  width: 300px;
  object-fit: contain;
}

.container {
  display: flex;
  height: 2em;
  width: 300px;
  padding: 1em;
  justify-content: space-around;
}
</style>
