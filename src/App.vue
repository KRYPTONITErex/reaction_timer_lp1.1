<template>

  <h2>HOW FAST you are CATCHING ?? </h2>
  <button @click="start" :disabled="isPlaying"> PLAY NOW </button>

  <div v-if="isPlaying">

    <Block :delay="delay" @endGame="endGame"></Block>

  </div>

  <!-- <p>result is {{ score }} milliSeconds</p> -->

    <div v-if="end">
      <Result :score="score"></Result>
    </div>

</template>

<script>

import Result from './components/Result'
import Block from './components/Block'
export default {
  name: 'App',
  components: {
    Result,
    Block,

  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      end: false

    }
  },
  methods: {
    start(){
      this.isPlaying = true;
      // console.log((2000+Math.random()*5000));
      this.delay = 2000+Math.random()*5000;
    },
    endGame(score){
      console.log(score)
      this.score = score
      this.isPlaying = false
      this.end=true
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h2 {
  font-size: 2rem;
  color: #34495e;
  margin-bottom: 20px;
}

button {
  background-color: #3498db;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #2980b9;
}

button:disabled {
  background-color: #95a5a6;
  cursor: not-allowed;
}

div {
  margin: 20px 0;
}

</style>
