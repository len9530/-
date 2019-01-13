<template>
	<div>
		<header>
			<div class="hearder">请发表对Vue的评论</div>
		</header>
		<Add :addComment="addComment"/>
		<List :comments="comments" :deleteComment="deleteComment"/>
	</div>
</template>

<script>
	import Add from './components/Add.vue'
	import List from './components/List.vue'

	export default {
		data() {
			return {
				comments:[
					{
						name:'AAA',
						comment: 'Vue真好用!'
					},
					{
						name:'BBB',
						comment: 'Vue有点难!'
					},
					{
						name:'CCC',
						comment: 'Vue还好吧!'
					}
				]
			}
		},
		components: {
			Add,
			List
		},
		methods:{
			addComment(comment) {
				this.comments.unshift(comment)
			},
			deleteComment(index) {
				this.comments.splice(index,1)
			}
		}
	}
</script>

<style>
	.hearder {
		height: 200px;
		background-color: #eee;
		font-size: 50px;
		text-align: center;
		line-height: 200px;
	}
</style>