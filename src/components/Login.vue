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
                    
                    <button type="submit" class="btn btn-balock btn-success"> 登录</button>
                </form>
            </div>
        </div>
    </div>
</div>
</template>

<script>
    export default {
        name: "Login",
        data(){
            return {
                email:'',
                password:''
            }
        },
        methods:{
            onSubmit(){

            }
        }
    }
</script>

<style scoped>

</style>

