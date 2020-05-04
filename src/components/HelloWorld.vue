<template>
  <div class="hello">
    <div>{{test}}</div>
    <button @click="getTest">test button</button>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'HelloWorld',
  data(){
    return {
      test:"null",
    }
  },
  methods: {
    getTest: function(){
      axios.get('http://i02d109.p.ssafy.io:7070/recipe/predict').then(res => {
        this.test = res.data.test;
      }).catch((err)=>{
        this.test = err;
      })
    },
  },
}
</script>