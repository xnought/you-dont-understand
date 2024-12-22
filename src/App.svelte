<script lang="ts">
	import { Router, Route, link } from "svelte-routing";
	import Title from "./lib/Title.svelte";
	import { articles } from "./articles/metadata";

	const basepath = "you-dont-understand";
</script>

<Router {basepath}>
	<!-- Home page with links to each article route -->
	<Route path="/">
		<article>
			<h1>You Don't Understand</h1>

			<section>
				<ul>
					{#each articles as a}
						<li><a href={a.link} use:link>{a.title}</a></li>
					{/each}
				</ul>
			</section>
		</article>
	</Route>

	<!-- Each route to an article -->
	{#each articles as a}
		<Route path={a.link}>
			<article>
				<Title title={a.title}></Title>
				<svelte:component this={a.component} />
			</article>
		</Route>
	{/each}
</Router>

<style>
</style>
