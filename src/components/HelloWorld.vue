<template>
  <div class="hello">
    <h1>{{ msg }} ,{{load}}</h1>
    <class1 />
    
  </div>
</template>

<script>
import class1 from './class1'
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    load: String
  },
  components:{
    class1
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
