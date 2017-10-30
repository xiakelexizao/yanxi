<template>
  <div>
     <button @click="add"></button>
     <span>大爷</span>
  </div>
</template>

<script>
    import axios from 'axios';
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
    methods:{
       add(){
           axios.get('http://localhost:3000/yanxi/find')
        .then(function(response){
          console.log(response,99);
        }).catch(function(err){
          console.log(err);
        });
       }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
