<script>
import { RouterLink } from 'vue-router';
export default {
  name: 'Header',
  
};
</script>


<template>
    
        <div class="nav">
            <P>Mini Ex</P>        
        </div>

</template>

<style>
    .nav {
        background-color: #FFFF;
        height: 100px;
        
        display: flex;
        align-items: center;
        
        border-bottom-left-radius: 8px;
        border-bottom-right-radius: 8px;
        
    }

</style>


<!-- <nav>
                <RouterLink to="/">Home</RouterLink>
                <RouterLink to="/dashboard">Dashboard</RouterLink>
                <RouterLink to="/login">Login</RouterLink>
            </nav> -->

