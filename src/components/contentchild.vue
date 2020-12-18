<template>
    <div>
        <div class="container">
                     <div class="row">
                        <div class="col-md-7">
                            <div class="shadow-sm">
                                <table class="table border-0">
                                    <thead>
                                       <th>{{nameFromContent.name}}</th>
                                       <th>{{nameFromContent.dept}}</th>
                                       <th>{{nameFromContent.sch}} </th>
                                       <th><span><button class="del-btn" v-on:click="$emit('del-stud',nameFromContent.nameid)">X</button></span></th>
                                       <!-- <th><button class="del-btn" v-on:click="('edit-stud')">E</button></th>
                                        -->
                                        <th><span><button class="del-btn" v-on:click="editNewName(nameFromContent)">E</button></span></th>
                                    </thead>
                                </table>
                            </div>
                        </div>
                    </div>
                    <!-- </table> -->
                <!-- </div> -->
            <!-- </div> -->
         <!-- </div> -->
         </div>
         <div>
            
            <button type="submit">Update</button>
         </div>
    </div>
</template>
<script>

export default {
    name:"Contentchild",
  
    props:['nameFromContent'],
    // data() {
    //     return {
    //         ename:'',
    //         edept:''
    //     }
    // },
    // methods:{
    //     editNewName(k){
    //     alert(k.name)
    //     // this.details= k
    //     this.ename = k.name
    //     this.edept = k.dept
    //     // console.log(newstud);
    //   }
    // }
}
</script>
<style  scoped>
    .del-btn{
        background: red;
        outline: none;
        border: 2px solid red;
        border-radius: 50%;
        color: white;
        font-weight: 700;
    }
    table{
        width: 370% !important;
    }
</style>
