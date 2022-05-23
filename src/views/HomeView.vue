<template>
  <h1>Home</h1>
  <div>ここにそれぞれのアプリに行けるリンクを設置する</div>
  <div class="link">
    <router-link to="/quiz" class="quizHome common">
      <p class="Text">クイズ</p>
    </router-link>

    <router-link to="/palette" class="paletteHome common">
      <p class="Text">パレット</p>
    </router-link>

    <router-link to="/memo" class="memoHome common">
      <p class="Text">メモ</p>
    </router-link>
  </div>
</template>

<style>
.link {
  width: 900px;
  margin: 100px auto;
  display: flex;
  justify-content: space-around;
}

.common {
  display: block;
  text-decoration: none;
  height: 200px;
  width: 200px;
  background-color: rgb(116, 195, 244);
  border-radius: 10px;
}

.quizHome:hover {
  box-shadow: -9px 9px 23px rgba(230, 180, 15, 0.9),
    9px -9px 23px rgba(137, 241, 133, 0.9);
}

.paletteHome:hover {
  box-shadow: -9px 9px 23px rgba(255, 140, 91, 0.9),
    9px -9px 23px rgba(230, 180, 15, 0.9);
}

.memoHome:hover {
  box-shadow: -9px 9px 23px rgba(253, 102, 94, 0.9),
    9px -9px 23px rgba(255, 142, 229, 0.9);
}

.Text {
  font-size: 20px;
  font-weight: bold;
  color: white;
  text-align: center;
  margin: 80px 0;
}
</style>
