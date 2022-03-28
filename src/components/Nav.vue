<script setup>
import {useRouter} from "vue-router";
import useAuth from "../composable/useAuth";
const { isAuthenticated, logout } = useAuth();
const router = useRouter();
const loggingOut = () => {
  logout();
  router.push("/");
};
</script>
<template>
<div class="bg-gradient-to-r from-sky-500 to-indigo-500 text-black-200">
    <div class="container mx-auto flex items-center">
        <h1 class=" px-6 font-medium tracking-wider text-4xl ">THRUST</h1>
        <nav>
            <ul class="flex space-x-4">
                <router-link to="/"><li class="py-8 px-4 hover:cursor-pointer hover:bg-gray-500 hover:text-gray-800">
                    Home</li>
                </router-link>


                <router-link :to="{name:'Hello'}"><li class="py-8 px-4 hover:cursor-pointer hover:bg-gray-500 hover:text-gray-800">Support</li></router-link>

                <router-link :to="{name:'Tournaments'}"><li class="py-8 px-4 hover:cursor-pointer hover:bg-gray-500 hover:text-gray-800">Tournaments</li></router-link>


                  <router-link v-if= "!isAuthenticated" :to="{path:'/login', name:'Login'}"><li class="py-8 px-4 hover:cursor-pointer hover:bg-red-500 hover:text-red-800">Login</li></router-link>

                  <div v-else class="flex">
                    <router-link :to="{path:'/secret', name:'Brackets'}"><li class="py-8 px-4 hover:cursor-pointer hover:bg-red-500 hover:text-red-800">Brackets</li></router-link>
                    
                    <button @click="loggingOut">
                    <li
                    class="px-4 py-8  hover:cursor-pointer hover:bg-indigo-500 hover:text-indigo-800"
                    >
                    Logout
                    </li>
                </button>
                </div>
                 <router-link :to="{name:'About'}"><li class="py-8 px-4 hover:cursor-pointer hover:bg-gray-500 hover:text-gray-800">FAQ</li></router-link>
            </ul>
        </nav>
    </div>
</div>
</template>