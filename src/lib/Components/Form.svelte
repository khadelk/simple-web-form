<script>
	import { slide } from 'svelte/transition';
	import { json } from '$lib/stores';
	import { goto } from '$app/navigation'

	const submit = (e) => {
		let data = new FormData(e.target)
		$json = Object.fromEntries(data.entries());
		goto('./thanks')
	}
</script>

<form transition:slide on:submit|preventDefault={(e) => {submit(e)}}>
	<div class="form-heading">
		<h1>Hire me!</h1>
		<h2>Fill out this form if you agree that Critical Mass should hire me.</h2>
	</div>
	<!-- Full Name -->
	<div class="input-padding">
		<label for="name">Full Name (required)</label>
		<div>
			<!-- Adding attribute "required" will ensure form cannot be submitted without the name -->
		<input name="name" type="text" autocomplete="name" required>
		</div>
	</div>

	<!-- Email -->
	<div class="input-padding">
		<label for="email">Email</label>
		<div>
			<!-- Adding type "email" ensures the email is in the correct format -->
		<input name="email" type="email" autocomplete="email">
		</div>
	</div>


	<div class="row-3">
	<!-- Address -->
	<div class="input-padding">
		<label for="address">Street Address</label>
		<div>
		<input name="address" type="text" autocomplete="street-address">
		</div>
	</div>

	<!-- City -->
	<div class="input-padding">
		<label for="city">City</label>
		<div>
		<input name="city" type="text" autocomplete="address-level2">
		</div>
	</div>
</div>

	<div class="row-4">
	<!-- State -->
		<div class="input-padding">
			<label for="state">State</label>
			<div>
			<input name="state" type="text" autocomplete="address-level1">
			</div>
		</div>

		<!-- Zip -->
		<div class="input-padding">
			<label for="zip">Zip Code </label>
			<div>
			<input name="zip" type="text" autocomplete="postal-code" title="Please use a five digit zip code" pattern="[0-9]*">
			<span class="zip">5 digits</span>
			</div>
			
		</div>
	</div>
	<button type="submit" value="submit" class="submit-button">Submit</button>

</form>