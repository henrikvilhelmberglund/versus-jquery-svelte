<script>
	import { page as pageStore } from '$app/stores';
	let { id, pageCount } = $props();
	const pages = $state(Array.from({ length: pageCount }, (_, i) => `/${i + 1}`));
	let selectedPage = $derived($pageStore.url.pathname);
</script>

<nav {id} class="pager">
	<a href="/" aria-current={selectedPage === '/' ? true : undefined}>Home</a>
	{#each pages as page}
		<a href={page} aria-current={selectedPage === page ? true : undefined} class="page">
			{page.at(1)}
		</a>
	{/each}
</nav>

<style>
	.pager {
		margin: 5px 10px;
		user-select: none;
		-webkit-user-select: none;
		font-family: sans-serif;
	}
	.pager .page {
		display: inline-block;
		padding: 0px 10px;
		cursor: pointer;
	}
	[aria-current] {
		font-weight: bold;
		color: FireBrick;
	}
</style>
