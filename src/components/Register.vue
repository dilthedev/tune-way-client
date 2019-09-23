<template>
    <div>
        <h1>Register</h1>
        <input type="email" name="email" placeholder="E-mail here" v-model="email">
        <br>
        <input type="password" name="password" placeholder="Password here" v-model="password">
        <br>
        <button @click="register">Register</button>
    </div>
</template>

<script>
/*eslint-disable*/
import AuthenticationService from '@/services/AuthenticationService'

export default {
    data() {
        return {
            email:'',
            password:''
        }
    },
    methods: {
       async register(){
            const response = await AuthenticationService.register({
                   email: this.email,
                   password:this.password
            }) 
            console.log(response.data);
            
        }
    },
    // watch: {
    //     email(value){
    //         console.log('email has changed to ',value);            
    //     }
    // },
    // mounted() {
    //     setTimeout(() => {
    //         this.email = 'hello world'
    //     }, 3000);
    // },
}
</script>

<style>

</style>