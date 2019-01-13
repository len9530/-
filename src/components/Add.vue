<template>
	<form action="" class="comment-l">
		<h5>请输入姓名:</h5>
		<input type="text" placeholder="请输入姓名" v-model="name">
		<h5>请输入评论:</h5>
		<textarea cols="30" rows="10" placeholder="请输入评论" v-model='content'></textarea><br>
		<button class="btn" v-on:click.prevent="add">提交</button>
	</form>
</template>

<script>
	export default {
		data() {
			return {
				name: '',
				content: ''
			}
		},
		props: {
			addComment: {
				type: Function,
				require: true
			}
		},
		methods: {
			add: function() {
				let comment = {
					name: this.name,
					comment: this.content
				}
				this.addComment(comment)
			}
		}
	}
</script>

<style>
	.comment-l {
		float: left;
		margin-left: 50px;
	}
	.btn {
		float: right;
	}
</style>