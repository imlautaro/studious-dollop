<script setup lang="ts">
definePageMeta({
	middleware: 'unauth',
})

const supaAuth = useSupabaseAuthClient().auth

const login = async () => {
	const { error } = await supaAuth.signInWithOAuth({
		provider: 'google',
		options: {
			redirectTo: 'http://localhost:3000/callback',
		},
	})

	if (error) {
		console.error(error.message)
	}
}
</script>

<template>
	<div>
		<h1>Login</h1>
		<button @click="login()">Login with Google</button>
	</div>
</template>
