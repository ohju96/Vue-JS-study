<template>

  <div class="menu">
    <a v-for="(test,i) in menus" :key="i">{{ test }}</a>
  </div>

  <div class="black-bg" v-if=" moStatus == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="moStatus = false">닫기</button>
    </div>
  </div>


  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 :style="roomColor" @click="moStatus = true">{{ rooms[0].title }}</h4>
    <p>{{ rooms[0].price }}원</p>
    <button @click="cnt[0]++">허위매물신고</button>
    <span>신고수 : {{ cnt[0] }}</span>
  </div>
  <div>
    <img :src="rooms[1].image" class="room-img">
    <h4 :style="roomColor" @click="moStatus = true">{{ rooms[1].title }}</h4>
    <p>{{ rooms[0].price }}원</p>
    <button @click="cnt[1]++">허위매물신고</button>
    <span>신고수 : {{ cnt[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 :style="roomColor" @click="moStatus = true">{{ rooms[2].title }}</h4>
    <p>{{ rooms[0].price }}원</p>
    <button @click="cnt[2]++">허위매물신고</button>
    <span>신고수 : {{ cnt[2] }}</span>
  </div>
</template>

<script>

import data from './oneroom';

export default {
  name: 'App',
  data(){
    return {
      rooms : data,
      moStatus : false,
      cnt: [0, 0, 0],
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      roomColor : 'color : blue',
    }
  },

  methods : {
    increase() {
      this.cnt += 1;
    }
  },

  components: {
  }
}
</script>

<style>

body {
  margin : 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
