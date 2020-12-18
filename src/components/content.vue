<template>
    <div>
        <div class="container">
         <h2>Our names</h2>
                <div class="row">
                    <div class="col-md-6 col-xl-6 col-lg-9">
                        <div class="shadow-sm">
                            <table class="table table-hover">
                                <thead>
                                    <th>Name</th>
                                    <th>Dept</th>
                                    <th>School</th>
                                    <th>delete</th>
                                    <th>Edit</th>
                                </thead>
                                <tbody class="tbody" >
                                    <tr  v-for="std in myName" v-bind:key="std.nameid"> 
                                        <td>{{std.name}}</td>
                                        <td>{{std.dept}}</td>
                                        <td>{{std.sch}} </td>
                                        <td><span><button class="del-btn" v-on:click="$emit('del-details',std.nameid)">X</button></span></td>
                                            <!-- <th><button class="del-btn" v-on:click="('edit-stud')">E</button></th>
                                                -->
                                        <td><span><button class="del-btn" v-on:click="editNewName(std)" data-toggle="modal" data-target="#myModal">E</button></span></td>
                                        <!-- <Contentchild class="col-xl-7 col-md-7 col-lg-7"  v-bind:nameFromContent="std" v-on:del-stud="$emit('del-details',std.nameid)"></Contentchild>-->
                                        <div class="modal" id="myModal">
                                            <div class="modal-dialog">
                                                <div class="modal-content">
                                                    <!-- Modal Header -->
                                                    <div class="modal-header">
                                                        <h4 class="modal-title">Modal Heading</h4>
                                                        <button type="button" class="close" data-dismiss="modal">&times;</button>
                                                    </div>
                                                    <!-- Modal body -->
                                                    <div class="modal-body">
                                                    Modal body..
                                                    <div class="form-group">
                                                    <!--<input type="text" class="form-control w-50 ml-2" width="50" v-model="edstudents.name"/>
                                                    <input type="text"  class="form-control w-50 ml-2 mt-3" width="50" v-model="edstudents.dept"/>
                                                     <input type="text"  class="form-control w-50 ml-2 mt-3" width="50" v-model="edstudents.sch"/>-->

                                                      <input type="text" class="form-control w-50 ml-2" width="50" v-model="name"/>
                                                    <input type="text"  class="form-control w-50 ml-2 mt-3" width="50" v-model="dept"/>
                                                     <input type="text"  class="form-control w-50 ml-2 mt-3" width="50" v-model="sch"/>
                                                    <input type="hidden" class="form-control w-50 ml-2" width="50" v-model="id"  value="nhdh"/>
                                                    </div>
                                                    </div>
                                                    <!-- Modal footer -->
                                                    <div class="modal-footer">
                                                    <button type="button" class="btn btn-danger" @click="update(edstudents)" data-dismiss="modal">Update</button>
                                                    </div>
                                
                                                </div>
                                            </div>
                                        </div>
                                   </tr>
                                </tbody>
                            </table>
                
                        </div>
                    </div>
                </div>
                <button type="button" data-toggle="modal" data-target="#myModal">uivufvbhfvbjh</button>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aliquid suscipit quaerat ab? Nam aut nihil quia recusandae fugit iure. Ab assumenda 
            veritatis incidunt soluta expedita tempora ducimus, dignissimos vitae accusantium?
        </div>
    </div>
</template>
<script>
// import Tablehead from "./table";
// import Contentchild from './contentchild'
export default {
    name:"Content",
    components:{
        // Contentchild,
        // Tablehead
    },
    data() {
        return {
            name:'',
            dept:'',
            sch:'',
            id:'',
            edstudents:{}
        }
    },
    props:["myName"],
     methods:{
        editNewName(k){
        alert(k.name)
        this.id= k.nameid
        this.name = k.name
        this.dept = k.dept
        this.sch = k.sch
        // let {name,dept,sch,nameid} = k
        this.edstudents={en:this.name,ed:this.dept,es:this.sch, ei:this.nameid}
        console.log(this.edstudents);
      },
      update(std){
            this.edstudents= std
        //   const updateStd = {en:this.ename, ed:this.edept, es:this.esch, eid:this.eid}
            console.log(this.edstudents)
          this.$emit('edit-dtl',std);
        //   console.log()
      }
    }
}
</script>
<style scoped>
    
</style>