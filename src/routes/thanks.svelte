<script>
	import { goto } from '$app/navigation';
	import { json } from '$lib/stores';
	import { slide } from 'svelte/transition';
	console.log($json);

</script>


<section class="thanks">
	<div transition:slide class="thanks">
		<h1>Thanks {$json.name}!</h1>
		<p>Here's the information you filled out:</p>
		<ul>
			{#each Object.keys($json) as key}
			<li>{key}: {$json[key]}</li>
			{/each}
		</ul>
		<button on:click={() => goto('/')}>Go back to form</button>

	</div>
</section>
