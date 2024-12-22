<script lang="ts">
	let { id } = $props();
</script>

<label for={id} class="margin-toggle sidenote-number"> </label>
<input type="checkbox" {id} class="margin-toggle" />
<span class="sidenote"><slot /></span>
