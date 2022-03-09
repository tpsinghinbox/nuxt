<template>
    <div>
     <Loader v-if="showHideSpinner" />    
    <h1>Hello User {{user.name}}</h1>
    <p>{{user.email}}</p>
     <p>{{user.phone}}</p>
     <p>https://insomnia.rest/</p>
     <NuxtLink to="/users">User</NuxtLink>
    </div>
</template>
<script>
export default {
    data(){
        return {
            user:{},
            //showHideSpinner: true
        }
        //this.$nuxt.$loading.start()

    },
    created(){
        fetch(`https://jsonplaceholder.typicode.com/users/${this.$route.params.id }`)
        .then(response => response.json())
        .then(json => {
            this.user = json
        })
    },
    beforeCreate() {
        this.$nuxt.$loading.start()
//        this.showHideSpinner = true;
    },
    mounted() {
        this.$nuxt.$loading.finish()
        //this.showHideSpinner = false;
    },
    
}
</script>