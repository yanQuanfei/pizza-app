<template>
<div>
    <h1>Home</h1>

    <button class="btn btn-success" @click="goToMenu">去菜单</button>
</div>

</template>

<script>
    export default {
        name: "Home",
        methods:{
            goToMenu(){
                // 跳转到上一个页面
                // this.$router.go(-1)
                //指定跳转
                // this.$router.replace('/menu')
                // 跳转到制定路由的名字
                // this.$router.replace({name:'menuLink'})

                // 通过push进行跳转
                this.$router.push('/menu')

            }
        }
            }
</script>

<style scoped>

</style>
