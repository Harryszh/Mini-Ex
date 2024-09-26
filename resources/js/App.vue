<script setup>
    import { RouterLink, RouterView } from "vue-router";
    import Header from './components/HeaderLogin.vue'
    import Footer from "./components/Footer.vue";
</script>

<template>
    <div class="main">
    
        <Header></Header>
    
        <RouterView />

        <Footer></Footer>

    </div>
</template>


    

<style>
    .main{
        height: 100%;
        margin: 0px;
        padding: 0px;

        display: flex;
        flex-direction: column;

        height: 852px;
        width: 393px;
        

        background-color: #D9D9D9;
    }
</style>
