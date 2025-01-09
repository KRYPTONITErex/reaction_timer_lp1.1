<template>
  <div class="box" v-if="showBox" @click="stopTimer">
    <p>CLICK NOW</p>
  </div>
</template>

<script>
export default {
    data(){
        return{
            showBox: false,
            score: 0,
            timer: null
        }
    },
    props: ['delay'],
    mounted(){
        setTimeout(()=>{
            this.showBox = true
            this.startTimer()
        },this.delay)
    },
    methods: {
        startTimer(){
            this.timer = setInterval(()=>{
                this.score += 50;
            },50)
        },
        stopTimer(){
           clearInterval(this.timer)
        //    console.log(this.score)
           this.$emit('endGame',this.score)
        }
    },

    updated(){
        console.log("DATA UPDATED")
    },
    unmounted(){
        console.log("unmounted the component")
    }
}
</script>

<style>
.box {
  display: inline-block;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 200px;
  background-color: #3498db;
  color: white;
  border-radius: 10px 0px 10px 0px;
  cursor: pointer;
  font-size: 1.5rem;
  font-weight: bold;
  text-transform: uppercase;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s, background-color 0.3s;
}

.box:hover {
  background-color: #2980b9;
  transform: scale(1.1);
}

.box:active {
  background-color: #1c5980;
  transform: scale(0.95);
}
</style>