<script setup lang="ts">
definePageMeta({
	middleware: 'auth',
})

const supabase = useSupabaseAuthClient()

const logout = async () => {
	const { error } = await supabase.auth.signOut()
	if (error) {
		console.error(error.message)
	} else {
		console.log('success')
	}
}
</script>

<template>
	<div>
		<h1>Admin</h1>
		<button @click="logout">Logout</button>
	</div>
</template>
