<template>
  <h1>Vue パレット</h1>
  <div class="app">
    <div
      class="palette"
      v-on:mousemove="colorPosition"
      v-on:click="colorDecision"
      v-bind:style="paletteColor"
    ></div>
    <p>rgba( {{ red }}, {{ green }}, 200, 0.5 )</p>
    <div class="colors-container">
      <div
        class="mini-palette"
        v-for="color in colors"
        v-bind:key="color.id"
        v-bind:style="{
          backgroundColor: `rgba(${color.red}, ${color.green},200, 0.5)`,
        }"
        v-on:click="detail"
      ></div>
    </div>
  </div>
</template>

<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
}
.palette {
  width: 270px;
  height: 270px;
}
.mini-palette {
  min-width: 60px;
  height: 60px;
}
.colors-container {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  padding-top: 8px;
}
</style>

<script src="https://unpkg.com/vue@next"></script>
<script>
Vue.createApp({
  data: function () {
    return {
      red: 0,
      green: 0,
      colors: [],
    }
  },
  methods: {
    colorPosition(position) {
      ;(this.red = position.offsetX), (this.green = position.offsetY)
    },
    colorDecision() {
      const colorHai = {
        red: this.red,
        green: this.green,
      }
      this.colors.push(colorHai)
    },
    detail() {
      this.red = color.red
      this.green = color.green
    },
  },
  computed: {
    paletteColor() {
      return {
        backgroundColor: `rgba(${this.red},${this.green},200,0.5)`,
      }
    },
  },
})
</script>
