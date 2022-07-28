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
	<!-- Full Name -->
	<div>
		<label for="name">Full Name</label>
		<div>
		<input name="name" type="text" autocomplete="name">
		</div>
	</div>

	<!-- Email -->
	<div>
		<label for="email">Email</label>
		<div>
		<input name="email" type="text" autocomplete="email">
		</div>
	</div>

	<!-- Address -->
	<div>
		<label for="address">Street Address</label>
		<div>
		<input name="address" type="text" autocomplete="street-address">
		</div>
	</div>

	<!-- City -->
	<div>
		<label for="city">City</label>
		<div>
		<input name="city" type="text" autocomplete="address-level2">
		</div>
	</div>

	<!-- State -->
	<div>
		<label for="state">State</label>
		<div>
		<input name="state" type="text" autocomplete="address-level1">
		</div>
	</div>

	<!-- Zip -->
	<div>
		<label for="zip">Zip</label>
		<div>
		<input name="zip" type="text" autocomplete="postal-code">
		</div>
	</div>
	<button type="submit" value="submit">Submit</button>

</form>

<style>
	form {
		height: auto;
		/* width: 50%; */
		margin-right: 0.5rem;

	}
	form > div {
		/* border: 1px solid black; */
	}

	form > div > div {
		margin-top: 1px;
	}

	form > div > div > input {
		-webkit-appearance: none;
		width: 100%;
		padding: 0.5rem;
		border: 1px solid #000;
		border-radius: 0.5rem;
		
	}

	@media only screen and (min-width: 500px) {
		form {
			width: 50%;
			margin: auto;

		}

}
</style>