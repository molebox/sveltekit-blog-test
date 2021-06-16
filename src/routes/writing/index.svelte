<script context="module">
	const pages = import.meta.glob('./*.svx');
	let body = [];

	for (const path in pages) {
		body.push(pages[path]().then(({ metadata }) => metadata));
	}

	/**
	 * @type {import('@sveltejs/kit').Load}
	 */
	export async function load({ page }) {
		const posts = await Promise.all(body);
		console.log({ posts });
		console.log(page.path);

		posts.sort((a, b) => (a.date > b.date ? -1 : 1));

		return {
			props: {
				posts
			}
		};
	}
</script>

<script>
	export let posts;
</script>

<div class="wrapper">
	<ul>
		{#each posts as post}
			<li>
				<a href="/writing/{post.slug}">{post.title}</a>
			</li>
		{/each}
	</ul>
</div>

<style>
	.wrapper {
		background: magenta;
		height: 100vh;
	}
</style>
