<template>
	<p>The User is {{ age }} years old</p>
</template>

<script>
export default {
	name: "UserItem",
	props: ["age"],
};
</script>

<style scoped lang="scss"></style>
