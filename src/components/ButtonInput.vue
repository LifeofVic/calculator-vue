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