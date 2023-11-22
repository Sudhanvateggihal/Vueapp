<template>
    <img class="logo" src="../assets/alchemist.jpg"/>
    <h1>SignUp</h1>
    <div class="register">
        <input type="text" v-model="name" placeholder="Enter Name"/>
        <input type="text" v-model="email" placeholder="Enter Email"/>
        <input type="password" v-model="password" placeholder="Enter Password"/>
       
        <router-link to="/Login"> <button v-on:click="SignUp">SignUp</button></router-link>
        <hr>
        <p>
            already have account?
            <router-link to="/Login">Login</router-link>
        </p>
    </div>
</template>

<script>
import axios from 'axios'
export default{
    name:'SignUp',
    data()
    {
        return{
            name:'',
            email:'',
            password:''
        }
    },
    methods:{
        async SignUp()
        {
           let result = axios.post("http://localhost:3000/users",{
                email:this.email,
                password:this.password,
                name:this.name
           });

           console.warn(result);
           if(result.status==201)
           {
            localStorage.setItem("user-info",JSON.stringify(result.data))
            this.$router.push({name:'Home'})
           }
        }
    },
    mounted()
    {
        let user=localStorage.getItem('user-info');
        if(user)
        {
            this.$router.push({name:'Home'})
        }
    }
}
</script>