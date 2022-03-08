<template>
    <div>

        <h1>Hello User {{user.name}}</h1>
    <p>{{user.email}}</p>
     <p>{{user.phone}}</p>
     <NuxtLink to="/users">User</NuxtLink>
    </div>
</template>
<script>
export default {
    data(){
        return {
            user:{}
        }
    },
    created(){
        fetch(`https://jsonplaceholder.typicode.com/users/${this.$route.params.id }`)
        .then(response => response.json())
        .then(json => {
            this.user = json
        })
    }
}
</script>