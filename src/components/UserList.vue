<template>
	<div>
	<h4 v-if="loading">Loading...</h4>
	<user-item
		v-for="user in result?.users"
		:key="user.id"
		:user="user"
	></user-item>
	</div>
</template>

<script>
	import { useQuery } from "@vue/apollo-composable";

	import {ALL_USERS_QUERY} from "../constants/graphql";

	import UserItem from './UserItem'

	export default {
		name: 'UserList',
		components: {UserItem},
		setup () {
			const { result, loading, error } = useQuery(ALL_USERS_QUERY);
			console.log("result: ", result);
			return {
				result,
				loading, 
				error,
			}
		}
	}
</script>