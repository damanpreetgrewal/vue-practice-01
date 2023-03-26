<template>
	<p v-if="age > 25">{{ msg }}</p>
	<p v-else>You must be 25 years or older to view this message</p>
	<p>{{ ageDoubled }}</p>
	<button type="button" @click="ageChangeFn(4)">Increment age</button>
	<button type="button" @click="decreseAge">decrement age</button>
</template>

<script>
export default {
	name: "GreetingItem",
	data() {
		return {
			msg: "Hello World!",
		};
	},
	props: {
		age: {
			type: Number,
			// required: true,
			// default: 20,
			validator(value) {
				return value < 130;
			},
		},
		ageChangeFn: Function,
	},
	computed: {
		ageDoubled() {
			return this.age * 2;
		},
	},
	methods: {
		onClickAge() {
			this.$emit("age-change", 3);
		},
		decreseAge() {
			this.$emit("low-age", 5);
		},
	},
};
</script>

<style scoped lang="scss">
$color: hsl(0deg, 100%, 50%);

p {
	color: $color;
}
</style>
