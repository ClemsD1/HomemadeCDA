<script setup lang="ts">
import { onMounted } from 'vue'
import { useUserStore } from './stores/userStore'
import Nav from './components/Nav.vue'

const userStore = useUserStore()

onMounted(() => {
  userStore.loadFromLocalStorage()
})
</script>

<template>
  <Nav v-if="userStore.isLoggedIn()" />
  <router-view />
</template>

<style scoped>
</style>
