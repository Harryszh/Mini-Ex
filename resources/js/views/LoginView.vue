<script setup>
import { ref } from "vue";
import { useAuthStore } from "@/store/AuthStore";
import router from "@/router";
/* import {HeaderLogin} from "../components/HeaderLogin.vue" */

const { login, getAuthUser } = useAuthStore();

const email = ref("test@example.com");
const password = ref("password1234");

const handleLogin = async () => {
    // wir geben die email und password Werte an die login Funktion in unserem Store weiter
    await login({ email: email.value, password: password.value });

    // nach dem Login holen wir uns den authentifizierten User um ihn im Store zu speichern
    const res = await getAuthUser();

    // wenn der Status 200 ist, leiten wir den Benutzer auf die Dashboard-Seite weiter
    if (res.status === 200) router.push("/dashboard");
};
</script>
<template>
    <div class="main-container">
        <!-- <div>
            <HeaderLogin/>
        </div> -->
        
        <div>
            <h1>Direkthandeln</h1>
            <p>Willkomen zurück</p>
        </div>
        
        <div class="login-box">
            <form @submit.prevent="handleLogin">
                <div>
                    <label class="label" for="email">Email:</label>
                    <input class="input" type="text" v-model="email" />
                </div>
                <div>
                    <label class="label" for="password">Password:</label>
                    <input class="input" type="password" v-model="password" />
                </div>
                <div>
                    <button type="submit">Login</button>
                </div>
                <div>
                    <p>
                        Wenn du noch keinen Account hast
                    </p>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>
   

    
    .main-container{
        display: flex;
        flex-direction: column;

        height: 852px;
        width: 393px;
        

        background-color: #D9D9D9;
    
    }
    .login-box{
        background-color: #FFFF;
        margin-left: 5%;
        margin-right: 5%;
        grid: 10px;

        /* display: flex;
        flex-direction: column; */
    }
    .label{
        padding: 3%;
    }
    .input{
        display: flex;
        flex-direction: column;
        
    }

</style>
