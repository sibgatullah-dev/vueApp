<template>
    <nav class="bg-[#ddd] py-4">  
        <div class="w-[1170px] m-auto">
            <div class="flex">
            <div class="logo w-[30%]">
                <div class="logo">
                    <img src="../assets/VUElogo.svg" width="50" alt="">
                </div>
            </div>
            
            <div class="menu w-[70%] ">
                <div class="menu">
                    <ul class="flex justify-end gap-4">
                        <li>
                            <router-link to="/">Home</router-link>
                        </li>
                        <li>
                            <router-link to="/about">About</router-link>
                        </li>
                        
                        <li><a href="">Contact</a></li>
                    </ul>
                </div>
            </div>
            </div>
        </div>
    </nav>
    <router-view></router-view>
</template>

<script setup>
import Home from '../pages/Home.vue'
import About from '../pages/About.vue'

component:{Home,About}
</script>