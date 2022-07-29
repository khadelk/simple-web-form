<script>
	import { json } from '$lib/stores';
	import { goto } from '$app/navigation'

	const submit = (e) => {
		let data = new FormData(e.target)
		$json = Object.fromEntries(data.entries());
		goto('./thanks')
	}
</script>

<form on:submit|preventDefault={(e) => {submit(e)}}>
	<div class="form-heading">
		<h1>Hire me!</h1>
		<h2>Fill out this form if you agree that I should be hired.</h2>
	</div>
	<!-- Full Name -->
	<div class="input-padding">
		<label for="name">Full Name</label>
		<div>
		<input name="name" type="text" autocomplete="name">
		</div>
	</div>

	<!-- Email -->
	<div class="input-padding">
		<label for="email">Email</label>
		<div>
		<input name="email" type="text" autocomplete="email">
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
			<label for="zip">Zip</label>
			<div>
			<input name="zip" type="text" autocomplete="postal-code">
			</div>
		</div>
	</div>
	<button type="submit" value="submit" class="submit-button">Submit</button>

</form>