<template>
	<greeting-item
		:age="age"
		:ageChangeFn="updateAgeCB"
		@age-change="updateAge"
		@low-age="decreaseAge"
	></greeting-item>
	<user-item :age="age"></user-item>
</template>

<script>
import GreetingItem from "./components/Greeting.vue";
import UserItem from "./components/User.vue";
export default {
	name: "App",
	components: {
		GreetingItem,
		UserItem,
	},
	data() {
		return {
			age: 20,
		};
	},
	methods: {
		updateAge(num) {
			this.age += num;
		},
		decreaseAge(num) {
			this.age -= num;
		},
		updateAgeCB(num) {
			this.age += num;
		},
	},
};
</script>
