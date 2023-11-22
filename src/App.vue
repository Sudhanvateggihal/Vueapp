<template>
  <router-view />
</template>

<script>


export default {
    name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: greyscale;
  text-align: center;
  color: #5e230a;
}
body{
  padding: 0;
  margin: 0;
  background-color: rgb(208, 208, 206);
}
.logo{
    width: 150px;
    border: 3px solid;
    color: rgba(200, 200, 203, 0.622);
    margin-top: 20px;
}
.register input,.login input{
    width: 350px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border-radius: 4px;
    border: 3px solid rgb(91, 87, 90);
}
.register button,.login button{
    width: 160px;
    height: 40px;
    border: 2px solid rgb(98, 97, 98);
    background:rgba(9, 206, 241, 0.873);
    color: black;
    cursor:pointer;
    border-radius: 10px;
    padding-left: 10px;
    margin-right: 8px;
}
</style>