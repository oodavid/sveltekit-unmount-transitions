<script>
  import { page } from '$app/stores';
	import { quintOut } from 'svelte/easing';
	import { scale } from 'svelte/transition';

	const options = [
		{ value: 1, title: 'one' },
		{ value: 2, title: 'two' },
		{ value: 3, title: 'three' },
	];
	
	let selected = 1;
</script>

<h2>Component {$page.params.someId}</h2>
{#each options as option}
	{#if option.value == selected}
		<div transition:scale={{ easing: quintOut }}>
			{option.value} : {option.title}
		</div>
	{/if}
{/each}

<style>
	div {
		border: 1px solid red;
		padding: 10px;
	}
</style>

<slot />