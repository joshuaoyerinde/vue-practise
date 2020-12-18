<template>
    <div>
    <div class="row justify-content-center mt-4">
        <div class="col-xl-5 col-md-5 col-lg-5">
            <div class="form-group">
                <input type="text" v-model="name"  name="inp" class="form-control" placeholder="add names.......">
                <input type="text" v-model="dept"  name="inp" class="form-control" placeholder="add names.......">
                <input type="text" v-model="school"  name="inp" class="form-control" placeholder="add names.......">
                <input @click="addStdName" type="button" value="Add" class="btn btn-light shadow-sm float-right mt-2">
                <div class="clearfix"></div>
            </div>
        </div>
    </div>
        
    </div>
</template>
<script>
// import uuid from 'uuid'<input type="text" v-on:change="setName"  name="inp" class="form-control" placeholder="add names.......">
let newkey = 0;
export default {
    name:"Addname",
    // props:["myName"],
    data() {
        return {
            // setName:''
            // id: this.data,
             name:'',
             dept:'',
             school:''
        }
            // this.addStdName(f)
    },
    methods:{
        
        // setName(event){
        //    this.name = event.target.name= event.target.value;
        //    this.dept= event.target.value
        // event.target.name=event.target.value
        // e
        // console.log(event.target.name)
        // },
        addStdName(){
         let newstdname = {
             nameid:newkey++,
              name:this.name,
              dept:this.dept,
              sch: this.school
         }
         this.name=''
         this.dept=''
         this.school=''
        //  console.log(newstdname)
            this.$emit('add-name',newstdname)
        },
        editg(){
            this.$emit('edit',this.name,this.dept,this.school)
        }
        
    }

}
</script>
<style scoped>
    
</style>