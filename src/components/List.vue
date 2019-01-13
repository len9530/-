<template>
	<div class="comment-r">
		<Item :comments="comments" :deleteComment="deleteComment"/>
	</div>
</template>

<script>
	import Item from './Item.vue'

	export default {
		props: {
			comments: Array,
			deleteComment: {
				type: Function,
			}
		},
		components: {
			Item
		}
	}
</script>

<style>
	.comment-r {
		width: 60%;
		float: left;
		margin-left: 20px;
	}
</style>