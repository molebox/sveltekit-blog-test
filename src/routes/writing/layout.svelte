<script>
	export let title;
	export let date;
</script>

<article class="post">
	<h1>{title}</h1>
	<p>Published: {date}</p>
	<slot />
	<a href="/">Back home</a>
</article>

<style>
	.post {
		background: plum;
		height: 100vh;
		margin: 0;
		padding: 0;
	}
</style>
