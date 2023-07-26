<script setup lang="ts">
const user = useSupabaseUser()

watch(user, (newValue, oldValue) => {
	if (oldValue === null && newValue !== null) {
		navigateTo('/admin')
	}
	if (!!oldValue && !newValue) {
		navigateTo('/login')
	}
})
</script>

<template>
	<div>
		<NuxtLayout>
			<NuxtPage />
		</NuxtLayout>
	</div>
</template>
