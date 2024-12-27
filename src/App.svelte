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
			<h1>You Don't Understand [insert topic]</h1>
			<p class="subtitle">By Donny Bertucci</p>

			<section>
				<p>
					The entire blog is just trying to convince you and me that
					the stuff we take for granted as being easy is actually
					insanely weird if you really think about it. We've just
					gotten used to them, no matter how arbitrary.
				</p>
				<blockquote>
					<p>
						Young man, in mathematics you don't understand things.
						You just get used to them.
					</p>
					<footer>John Von Neumann</footer>
				</blockquote>
				<p>Click on a blog below ↓</p>
				<ul>
					{#each articles as a}
						<li>
							<p>
								<a href={a.link} use:link
									><span style="font-size:smaller;"
										>You Don't Understand
									</span>
									<b>{a.title}</b></a
								>
							</p>
						</li>
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
