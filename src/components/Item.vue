<template>
	<div>
		<dl v-for="(comment,index) in comments" :key="index" >
			<dt>{{ comment.name }}说：</dt>
			<dd>{{ comment.comment }}</dd>
			<button class="deleteBtn" @click="rm(index)">删除</button>
		</dl>
	</div>	
</template>

<script>
	export default {
		props: {
			comments: Array,
			deleteComment: {
				type: Function,
			}
		},
		methods: {
			rm: function(index) {
				this.deleteComment(index)
			}
		}
	}
</script>

<style>
	dl {
		min-height: 100px;
		border: 1px solid #000;
		position: relative;
	}
	.deleteBtn {
		float: right;
		position: absolute;
		top: 0;
		right: 0;
	}

</style>