<script setup lang="ts">
import { AuthModal } from '#components'
const modal = useModal()

function openModal() {
    modal.open(AuthModal)
}


</script>

<template>
    <nav class="fixed w-full py-3 px-4 bg-gray-800">
        <div class="flex items-center justify-between">
            <NuxtLink to="/" external> 
                <NuxtImg src="/img/logo.png" alt="SkinBuddy" role="link" class="w-32 md:w-44" />
            </NuxtLink>
            <span class="text-xl text-white/70 hover:text-gray-100" role="button"
                @click="openModal">Login/Register</span>
        </div>
    </nav>
</template>
