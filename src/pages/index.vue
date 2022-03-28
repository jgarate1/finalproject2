<script setup>
import useAuth from "../composable/useAuth";
const { isAuthenticated, user } = useAuth();
</script>
<template>
    <div class="py-20 text-center text-white">
        <h1 class=" py-4 text-6xl">Tournaments hosted by <span class="tracking-wider font-medium">THRUST</span></h1>
    </div>
</template>