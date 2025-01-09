<template>

  <h1>Wanna play QUICKKIE</h1>
  <h2>Catch me if U CANN...</h2>
  <button @click="isPlaying" :disabled="play" >PLAY NOW</button>

  <div v-if="play">
    <Block @click="stopGame" :delay="delay" @endGame="endGame"></Block>
  </div>

  <div v-if="end">
    <Result :score="score"></Result>
  </div>
</template>

<script>

import Result from './components/Result'
import Block from './components/Block'
export default {
  data () {
    return{
      play: false,
      delay: null,
      score: 0,
      end: false
    }
  },
  components: {
    Result, Block },
  methods: {
    isPlaying(){
      this.play = true
      // console.log( 2000 + Math.random()*5000 )
      this.delay = 1500 + Math.random()*5000

    },
    stopGame(){
      this.play=false
    },
    endGame(score){
      console.log(score)
      this.score = score
      this.end = true
    }
  },


}
</script>

<style>
h1, h2 {
  text-align: center;
  font-family: 'Arial', sans-serif;
  color: #34495e;
  margin: 10px 0;
}

h1 {
  font-size: 2.5rem;
  font-weight: bold;
}

h2 {
  font-size: 1.8rem;
  font-weight: 500;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

button {
  display: block;
  margin: 20px auto;
  padding: 10px 20px;
  background-color: #27ae60;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

button:hover {
  background-color: #229954;
  transform: scale(1.05);
}

button:active {
  background-color: #1e8449;
  transform: scale(0.95);
}

div {
  margin-top: 20px;
  text-align: center;
}
</style>