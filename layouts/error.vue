<template>
	<div class="h-full text-center flex flex-col items-center justify-center">
		<div class="p-8">
			<h1 v-if="error.statusCode === 404">Космическая Станция 404</h1>
			<h1 v-else>УПС! Такой страницы не существует.</h1>
			<NuxtLink to="/">На главную</NuxtLink>
		</div>
	</div>
</template>

<script>
export default {
	name: 'ErrorLayout',
	props: {
		error: {
			type: null,
			default: null,
		},
	},
	head() {
		return {
			title: 'Error',
		}
	},
}
</script>
