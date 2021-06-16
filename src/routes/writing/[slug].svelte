<!-- THIS FILE IS NOT USED FOR SOME REASON!! -->

<script context="module">
	export async function load({ page }) {
		console.log({ page });
		const post = 'boop';

		return {
			props: {
				post
			}
		};
	}
</script>

<script>
	export let title;
</script>

<div class="wrapper">
	<h1>{title}</h1>
	<p>can you see me?</p>
	<slot />
</div>

<style>
	h1 {
		font-weight: bold;
	}
	.wrapper {
		padding: 1rem;
	}
</style>
