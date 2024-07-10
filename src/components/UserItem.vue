<template>
	<div>{{user.name}} ({{user.email}}) {{user.booksCount > 1 ? 'have' : 'has'}} {{user.booksCount}} {{user.booksCount > 1 ? 'books' : 'book'}}</div>
	<ul v-if="user.books">
		<li v-for="(book,index) in user.books" :key="index">{{book.title}}</li>
	</ul>
</template>
<script>
export default {
	name: 'UserItem',
		props: {user: {
				type: Object,
				required: true
			}
		}
	}
</script>