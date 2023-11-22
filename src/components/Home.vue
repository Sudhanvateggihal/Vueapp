<template>
    <Header />
    <h1>Hello</h1>
</template>

<script>
import Header from './Header.vue'
export default{
    name:'Home-Page',
    components:{
        Header
    },
    mounted()
    {
        let user=localStorage.getItem('user-info');
        if(!user)
        {
            this.$router.push({name:'Home'})
        }
    }
}
</script>