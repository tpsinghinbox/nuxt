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
export default {
    data(){
        return{
            title:'Users Listing',
            users:[]
        }
    },
    created(){
        fetch('https://jsonplaceholder.typicode.com/users')
        .then(response => response.json())
        .then(json => {
            this.users = json
        })
    }
    
}
</script>