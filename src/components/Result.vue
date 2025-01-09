<template>
  
    <h3>Your Score {{ score }} milliSeconds</h3>

    <div v-if="score<=300" id="fast"><p>Congratulations , You Got me TOO FAST</p></div>
    <div v-else-if="score>300 && score<=500" id="normal"><p>Normal Bro , Just Normal</p></div>
    <div id="slow" v-else><p>POOR man , You are TOO SLOWW</p></div>


</template>

<script>
export default {

    props: ['score']

}
</script>

<style>
h3 {
  text-align: center;
  font-family: 'Arial', sans-serif;
  color: #2c3e50;
  font-size: 1.8rem;
  margin-bottom: 20px;
}

#fast, #normal, #slow {
  text-align: center;
  font-family: 'Verdana', sans-serif;
  color: #34495e;
  font-size: 1.4rem;
  margin: 15px auto;
  padding: 10px;
  border-radius: 10px;
  width: 80%;
  max-width: 500px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

#fast {
  background-color: #27ae60;
  color: white;
}

#normal {
  background-color: #f39c12;
  color: white;
}

#slow {
  background-color: #e74c3c;
  color: white;
}

p {
  margin: 0;
  font-weight: bold;
  text-transform: uppercase;
}
</style>