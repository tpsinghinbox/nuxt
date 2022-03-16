<template>
<div>
    
    <h1>{{title}}</h1>    
    <ul>
        <li v-for="user in users" :key="user.id">
            <NuxtLink :to="'/users/'+user.id">{{user.name}}</NuxtLink>
        </li>
    </ul>
</div>
</template>

<script>
import axios from 'axios'
export default {

    data(){
        return{
            title:'Users Listing',
            users:[],
            
        }        
    },
    async fetch(){
        await this.getUsers();        
    },
    methods:{
       async getUsers(){
            const alldata = await axios.get('https://jsonplaceholder.typicode.com/users')
            alldata.data.forEach((user)=>{
                this.users.push(user)
            })
            //this.users = alldata.data
        }
    },
//     asyncData () {
//     return new Promise((resolve) => {
//         //this.fetch()
//     //   setTimeout(function () {
//     //     resolve({ name: 'world' })
//     //   }, 1000)
//     })
//   },
    // created(){
    //     fetch('https://jsonplaceholder.typicode.com/users')
    //     .then(response => response.json())
    //     .then(json => {
    //         this.users = json
    //     })
    // },
    async created(){       
       //const alldata = await axios.get('https://jsonplaceholder.typicode.com/users')
       //const alldata = await this.$axios.get('https://jsonplaceholder.typicode.com/users')
       //this.users = alldata.data

    }
    
}
</script>