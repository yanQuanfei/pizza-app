<template>
<div class="row mt-3">
    <div class="col-md-12 col-lg-12">
        <div class="code">
            <div class="code-body">
                <img class="mx-auto d-block" src="../assets/icon.png" alt="">
                <form @submit.prevent="onSubmit">
                    <div class="form-group">

                        <label for="email">邮箱</label>
                        <input type="email" name=""  class="form-control" v-model="email">
                    </div>
                    <div class="form-group">

                        <label for="password">密码</label>
                        <input type="password" name=""  class="form-control" v-model="password">
                    </div>
                    <div class="form-group">

                        <label for="confirm-password">确认密码</label>
                        <input type="password" name=""  class="form-control" v-model="confirmPassword">
                    </div>
                    <button type="submit" class="btn btn-balock btn-success"> 注册</button>
                </form>
            </div>
        </div>
    </div>
</div>
</template>

<script>

import axios from 'axios' 

    export default {
        name: "Register",
        data(){
            return {
                email:'',
                password:'',
                confirmPassword:''
            }
        },
        methods:{
            onSubmit(){
                if(this.password===this.confirmPassword)
                {
                    const fromData={
                        email:this.email,
                        password:this.password,
                        confirmPassword:this.confirmPassword
                    }
                    
                    axios.post('/users.json',FormData).then(res =>{
                        console.log(res)
                    })
                }
                else
                {
                    alert('两次密码不一致')
                }
                

            }
        }
    }
</script>

<style scoped>

</style>
