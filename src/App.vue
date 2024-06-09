<template>
	<div>
		<post-form :posts='posts'/>
		<post-list :posts="posts"/>
	</div>
</template>

<script>
	import PostList from '@/components/PostList.vue'
	import PostForm from '@/components/PostForm.vue'
	export default {
		components: {
			PostList, PostForm
		},
		data() {
			return {
				posts: [
					{id: 1, title: 'JavaScript', body: 'Описание поста'},
					{id: 2, title: 'JavaScript', body: 'Описание поста 2'},
					{id: 3, title: 'JavaScript', body: 'Описание поста 3'},
					{id: 4, title: 'JavaScript', body: 'Описание поста 4'},
				],
				title: '',
				body: '',
			}
		}
	}
</script>

<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
</style>