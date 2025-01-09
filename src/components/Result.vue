<template>
    <p>Your Result is {{ score }} milliSeconds</p>

    <div id="fast" v-if="score<=300"><p>You are too Fast bro !!</p></div>
    <div id="normal" v-else-if="score>300 && score<=500"><p>Normal bro, just normal.</p></div>
    <div id="poor" v-else><p>Oh poor man, you are too SLOWWW ..</p></div>
</template>

<script>
export default {
    props: ['score']
}
</script>

<style>
p {
  font-size: 1.5rem;
  color: #2c3e50;
  margin: 10px 0;
  text-align: center;
}

div {
  font-size: 1.2rem;
  font-weight: bold;
  color: #34495e;
  margin-top: 15px;
  text-align: center;
}
#fast p {
  color: #27ae60; /* Green for fast reaction */
}

#normal p {
  color: #f1c40f; /* Yellow for normal reaction */
}

#poor p {
  color: #e74c3c; /* Red for slow reaction */
}
</style>