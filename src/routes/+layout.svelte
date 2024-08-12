<script>
  import { page as pageStore } from '$app/stores';
	import Pager from '../lib/Pager.svelte';
	const { children } = $props();
  let selectedPage = $derived($pageStore.url.pathname);
  const pageCount = $state(5);
</script>

<svelte:head>
  <title>Versus JS - Svelte5 & SvelteKit - {selectedPage === "/" ? "Home" : selectedPage.at(1)}</title>
  <meta name="description" content="Silly benchmark comparison">
</svelte:head>

<Pager {pageCount} id="top_pager" />

<main id="content" class="paged-content">
	{@render children()}
</main>

<Pager {pageCount} id="bottom_pager" />

<style>
	.paged-content {
		font: bold 250% sans-serif;
		padding: 25px 10px;
	}
</style>
