<template>
    <div>
        <nav>
            <ul>
                <li> <router-link to="/">Home</router-link></li>
                <li>
                    <router-link to="/About">About</router-link>
                </li>
                <li>
                    <router-link to="/Contact">Contact</router-link>
                </li>
            </ul>
        </nav>

         <ul>
            <li v-for="(id,index) in UserIds" :key="index">
                <router-link :to="{name: 'Profile', params:{user_id: id}}">
                    Profile {{ id }}
                </router-link>
            </li>
        </ul>
        <button @click="Contact">Contact</button>
        <button @click="About">About</button>
        <div></div>
    </div>
</template>

<script>
export default {
    name: 'Navbar',
    data() {
        return {
            UserIds:['1','2','3','4','5','6','7','8']
        }
    },
    methods:{
        Contact (){
            this.$router.push({name: 'Contact'})
        },
         About (){
            this.$router.push({name: 'About'})
        },
    }
}
</script>

<style>
    nav{
        text-align: center;
    }
    nav ul{
        padding: 0;
    }
    nav li{
        list-style-type: none;
        padding: 8px;
        margin: 0;
        display: inline-block;
    }
    a.router-link-exact-active{
        color: red;
    }
</style>