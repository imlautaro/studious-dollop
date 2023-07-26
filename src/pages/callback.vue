<script setup lang="ts">
const timeout = ref<NodeJS.Timeout>()

onMounted(() => {
	timeout.value = setTimeout(() => {
		navigateTo('/')
	}, 3000)
})

onBeforeUnmount(() => {
	clearTimeout(timeout.value)
})
</script>

<template>
	<div>
		<h1>Redirecting...</h1>
	</div>
</template>
