<template>
    <div class="nav">
    <a href="#">Home</a>
    <a href="#">Department</a>
    <a href="#">Officers</a>
    <a v-on:click="logout" href="#">Logout</a>
   </div>
</template>

<script>
export default {
    name:'Header-Page',
    methods:{
        logout()
        {
           localStorage.clear();
           this.$router.push({name:'Login'})
        }
    }
}
</script>

<style>
.nav{
    background-color: rgb(140, 198, 109);
    overflow:hidden;
}
.nav a{
    float: left;
    color: rgb(3, 3, 3);
    padding: 14px 14px;
    text-align: center;
    font-size: 17px;
    text-decoration: none;
    margin-right: 5px;
    border-radius: 3px;      
}
.nav a:hover{
    background: rgb(168, 165, 165);
    color: rgb(73, 72, 73);
}
</style>