<template>
    <img class="logo" src="../assets/alchemist.jpg" />
    <h1>Login</h1>
    <div class="login">
        <input type="text" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <router-link to="/#"><button v-on:click="login">login</button></router-link>
        <hr>
        <p>
           New here?
           <router-link to="/SignUp">create new account</router-link>
        </p>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'LoginPage',
    data()
    {
        return{
            email:'',
            password:''
        }
    },
    methods:{
        async login()
            {
                let result=await axios.get(
                    'http://localhost:3000/users?email=${this.email}&password=${this.password}'
                )
                if(result.status==200 && result.data.length>0)
           {
            localStorage.setItem("user-info",JSON.stringify(result.data[0]))
            this.$router.push({name:'Home'})
           }
                console.warn(result)
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
};
</script>