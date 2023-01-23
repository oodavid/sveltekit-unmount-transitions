<script>
  import { page } from '$app/stores';
  import Transitions from './Transitions.svelte';
</script>

<h1>a/{$page.params.someId}/+layout.svelte</h1>

{#key $page.params.someId}
	<Transitions />
{/key}

<slot />