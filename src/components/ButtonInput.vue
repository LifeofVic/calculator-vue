<template>
	<button type="button" class="btn">
		{{ symbols }}
	</button>
</template>

<script>
export default {
	name: 'ButtonInput',
	props: {
		symbols: String
	}
}
</script>

<style >
button {
	width: 100px;
	padding: 10px;
	font-size: 16pt;
	border: black;
	color: white;
}
</style>