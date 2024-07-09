<template>
	<div>{{user.name}} ({{user.email}}) have {{user.booksCount}} books</div>
</template>
<script>
export default {
	name: 'UserItem',
		props: ['user']
	}
</script>