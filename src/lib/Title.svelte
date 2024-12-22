<script lang="ts">
	let { title }: { title: string } = $props();
</script>

<svelte:head>
	<title>You Don't Understand {title}</title>
</svelte:head>

<h1>{title}</h1>
