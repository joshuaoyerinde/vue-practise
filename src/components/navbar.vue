<template>
    <div>
        <nav class="navbar navbar-expand-md navbar-light bg-light shadow-sm">
            <div class="container">
             <a class="navbar-brand" href="#">Logo</a>
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <a href="#" class="nav-link">Home</a>
                    </li>
                     <li class="nav-item">
                        <a href="#" class="nav-link">About</a>
                    </li>
                     <li class="nav-item">
                        <a href="#" class="nav-link">Gallery</a>
                    </li>
                    <li class="nav-item">
                        <a href="#" class="nav-link">{{nameFromApp}}</a>
                    </li>
                </ul>
            </div>
        </nav>
    </div>
</template>
<script>
export default {
    name:"Navbar",
    props:[
            "nameFromApp"
        ],
    // components:{

    // }
}
</script>
<style scoped>
    
</style>