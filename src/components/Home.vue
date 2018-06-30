<template>
<div class="row">
<div id="home" class="col-sm-12 text-center">

    <div class="background">
        <h1>欢迎大家品尝 Pizza！</h1>
        <h2>这里有你喜欢的 Pizza</h2>

        <button class="btn btn-success" @click="goToMenu">去菜单</button>
    </div>
</div>

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
#home{
    background: url('../../src/assets/pizza.jpg');
    height: 80vh;
    padding: 10%;

}
h1,h2{
    margin: 6%;
}
.background{
    background: #eee;
    opacity: 0.8;
    max-width: 70vw;
    margin: 0 auto;
    padding: 20xp 0;
}

</style>
