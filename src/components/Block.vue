<template>
    <div class="block" v-if="showBlock" @click="stopTimer"> CLICK FASTT </div>

    <!-- <h3> result {{ score }}</h3> -->
  
</template>


<script>
export default {

    props: ['delay'],

    data(){
        return {
            showBlock: false,
            score:0,
            timer: null
        }
    },

    mounted(){
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer()
    },this.delay);
    },
    
    methods:{
        startTimer(){
            this.timer = setInterval(()=>{
                this.score += 50;
            },50)
        },
        stopTimer(){
            clearInterval(this.timer)
            // console.log(this.score)
            this.$emit("endGame",this.score)
        }
    },

    updated(){
        console.log("DATA UPDATED   ")
    },
    unmounted(){
        console.log("component unmounted")
    },
}
</script>


<style scoped>

.block{
  width: 400px;
  border-radius: 20px 0 20px 0;
  background: #12d3f0;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}


</style>