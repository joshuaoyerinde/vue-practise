<template>
  <div id="app">
  {{JSON.stringify(allsr)}}
    <!-- <Todos v-bind:todos="todos"/> -->
    <Navbar v-bind:nameFromApp="navname"/>

    <Addname v-on:add-name="addNewName"/>


    <Content v-bind:myName="details" v-on:del-details="delDetails" v-on:edit-dtl="updateDetails"/>
    <button @click="changename">changename</button>
    <Firstcomp/>

  </div> 
</template> 

<script>
// import Todos from './components/todo';
import Navbar from './components/navbar';
import Content from './components/content';
import Addname from './components/addname'
import Firstcomp from './components/firstcomp'
import Axios from "axios"
export default {
  name: 'App',
  components: {
    Navbar,
    Content,
    Addname,
    Firstcomp
  },
  data() {
    return {
      allsr:[],
      // todos:[
      //    {id: 1, title:"todo one", completed: false},
      //    {id: 2, title:"todo two", completed: true},
      //    {id: 3, title:"todo three", completed: true},
      // ],
      // details:[
          // {id:1, name:"olamide"},
          // {id:2, name:"olawale"},
          // {id:3, name:"Ademide"},
          // {id:4, name:"Olasanjor"},
          // {name:"Olasanjor"}
      // ],
       details:[ ],
      navname:"Help"
    }
  },
  methods:{
      changename(){
        this.navname="Our Vission";
        // alert(this.navname)
      },
      delDetails(id){ 
        this.details=this.details.filter(d => d.nameid !==id);
      },
      addNewName(newstdname){
       console.log(this.details= [...this.details,newstdname]) 
      },
      updateDetails(upd){
        
        //   this.details.map(function (details) {
        //    if(details.nameid == upd.nameid){
        //       // console.log(details.name);
        //       details.name = upd.name
        //       details.dept = upd.dept
        //       details.sch = upd.sch
        //       console.log(upd.name);
        //    }
        //  });
          this.details.forEach( details => {
           if(details.nameid == upd.ei){
              // console.log(details.name);
              details.name = upd.en
              details.dept = upd.ed
              details.sch = upd.es
              console.log(upd.name);
           }
         });
            // element.name= upd.ename
          
        // });
        // console.log( this.details)

      }
     
  },
  mounted(){
    let  url ="https://jsonplaceholder.typicode.com/users"
    Axios.get(url).then(res=>this.allsr=res.data);
  }
}
</script>

<style>

</style>
