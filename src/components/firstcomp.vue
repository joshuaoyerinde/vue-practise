<template>
    <div v-bind:style="{'background-color': bg}">
        <!-- <div v-if="verify">
            Display if im true
        </div> -->
        <div>
            <div v-bind:class="{'bg-danger text-white': num >30}">
            jhdfhurfguhui
            </div>
            <div v-bind:style="{'background-color': bg}">
            jhdfhurfguhui
            </div>
            <button @click="randomColor">Random color</button>
        </div>
        <div v-if="num<=0">
            lessthan Zero
        </div>
        <div v-else-if="num<=50">
            lessthan or = 50
        </div>
        <div v-else-if="num<=100">
            lessthan or = 100
        </div>
        <div v-else>
            num is greater than 100
        </div>
        <div>the current value s {{num}} </div>
            <!-- <button @click="verification">Verify</button> -->
            <button @click="addnum">Add</button>
            <button @click="reduce">Reduce</button>
    </div>
</template>
<script>
export default {
    name:"Firstcomp",
    data:()=>({
        num:10,
        verify: true,
        myColor:"green",
        bg:"yellow"
    }),
    methods:{
        // verification(){
        //     this.verify = !this.verify
        // }
        addnum(){
            this.num = this.num+3
        },
        reduce(){
            this.num = this.num-3
        },
        randomColor(){
            setInterval(() => {
                let myNum= Math.floor(Math.random()*4000000);
                this.bg=`#${myNum}`
                
            }, 200);
        }
    }
}
</script>
<style lang="css" scoped>

</style>