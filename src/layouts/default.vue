<script setup lang="ts">
const user = useSupabaseUser()
</script>

<template>
	<div>
		<NuxtLink to="/">Home</NuxtLink>
		<NuxtLink v-if="user" to="/admin">Admin</NuxtLink>
		<NuxtLink v-else to="/login">Login</NuxtLink>
		<slot />
	</div>
</template>
