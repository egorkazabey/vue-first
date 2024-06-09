<template>
	<div>
		<form @submit.prevent>
			<h4>Создание поста</h4>
			<input
				v-bind:value='post.title'
				@input='post.title = $event.target.value'
				class='input'
				type='text'
				placeholder='Название'
			/>
			<input
				v-bind:value='post.body'
				@input='post.body = $event.target.value'
				value='body'
				class='input'
				type='text'
				placeholder='Описание'
			/>
			<button class='btn' @click='createPost'>Создать пост</button>
		</form>
	</div>
</template>

<script>
export default {
	props: {
		posts: {
			type: Array,
		}
	},
	data() {
		return {
			post: {
				title: '',
				body: '',
			}
		}
	},
	methods: {
		createPost() {
			const newPost = {
				id: Date.now(),
				title: this.title,
				body: this.body,
			}
			this.posts.push(newPost)
			this.title = '';
			this.body = '';
		},
	}
}
</script>

<style scoped>
	form {
		display: flex;
		flex-direction: column;
		
	}
	.btn {
		align-self: flex-end;
		margin-top: 15px;
		padding: 10px 15px;
		background: none;
		border: 1px solid teal;
		cursor: pointer;
	}
	
	.input {
		width: 100%;
		border: 1px solid #ccc;
		padding: 10px 15px;
		margin-top: 15px;
	}
</style>