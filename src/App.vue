<template>
	<div>
		<div>
			<button @click="addLike">Like</button>
			<button @click="addDislike">Dislike</button>
		</div>
		<div>Количество лайков: <strong>{{ likes }}</strong></div>
		<div>Количество дизлайков: <strong>{{ dislikes }}</strong></div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			likes: 0,
			dislikes: 0,
		}
	},
	methods: {
		addLike() {
			return this.likes += 1;
		},
		addDislike () {
			return this.dislikes += 1;
		}
	}
}
</script>

<style>

</style>

