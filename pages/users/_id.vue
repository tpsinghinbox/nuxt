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
<<<<<<< HEAD
    beforeCreate() {
        //this.$nuxt.$loading.start()
        //this.showHideSpinner = true;
    },
    mounted() {
         //this.$nuxt.$loading.start()        
=======
    beforeCreate() {       
//        this.showHideSpinner = true;
    },
    mounted() {        
>>>>>>> 7a3c0d5de1f34ae0c390d81d71b973f98796a7bc
        //this.showHideSpinner = false;
    },
    
}
</script>