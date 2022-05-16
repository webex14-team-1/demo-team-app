<template>
  <h1>Vue クイズ</h1>
  <div class="app">
    <h2>Q. {{ "クイズタイトル" }}</h2>
    <img
      class="quiz-image"
      src="https://via.placeholder.com/300x300"
      alt="クイズタイトル"
    />
    <div class="container">
      <button>
        {{ "東京" }}
      </button>
      <button>
        {{ "千葉" }}
      </button>
      <button>
        {{ "神奈川" }}
      </button>
    </div>
    <div>{{ "千葉" }}</div>
  </div>
</template>

<script>
export default {}
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
