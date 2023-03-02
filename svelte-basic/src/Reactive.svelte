<script>
	let firstname = 'thara';
	let lastname = 'm p';

	$: fullName = `${firstname} ${lastname}` // reactive values (updates automatically when value changes)
	$: {
		console.log(colorInput)
	}
	let colorInput = 'red'
</script>

<main>

	<p>{fullName} - {colorInput}</p>	
	<!-- User inputs and databinding -->
	<!-- <input type="text" on:input={handleInput} value={colorInput}/> --> 
	<!-- Bind 2 ways instead of on:input and value -->
	<input type="text" bind:value={colorInput}/>
	<br />
    <input type="text" bind:value={firstname}/>
    <input type="text" bind:value={lastname}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #e7d25a;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>