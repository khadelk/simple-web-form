<script>
	import { goto } from '$app/navigation';
	import { json } from '$lib/stores';
	import { slide } from 'svelte/transition';
	console.log($json);
	const submittedValues = Object.keys($json).filter(key => $json[key].length > 0);
</script>


<section class="thanks">
	<div transition:slide class="thanks">
		<h1>Thanks {$json.name}!</h1>
		<p>Here are the values of the form you filled out:</p>
		<ul>
			{#each submittedValues as key}
			<li>{key}: {$json[key]}</li>
			{/each}
		</ul>
		<button on:click={() => goto('/')}>Go back to form</button>
	</div>
</section>
