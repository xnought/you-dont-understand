<script lang="ts">
	import katex from "katex";

	let { tex, displayMode = false }: { tex: string; displayMode?: boolean } =
		$props();

	let renderedHTMLString = $derived(
		katex.renderToString(tex, {
			throwOnError: false,
			displayMode,
		})
	);
</script>

{@html renderedHTMLString}
