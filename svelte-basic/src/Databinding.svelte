<script>
	let firstname = 'thara';
	let lastname = 'm p';

	$: name = firstname + ' ' + lastname // reactive values
	let colorInput = 'red'

	// named functions
	const handleClick = () => {
		colorInput = 'orange'
	}

	const handleInput = (e) => {
		colorInput = e.target.value
	}

	
</script>

<main>
	<h1>Hello {name}!</h1>

	<p style="color: {colorInput}">{colorInput}</p>

	<button on:click={handleClick}>Update color</button> 
	
	<!-- User inputs and databinding -->
	<!-- <input type="text" on:input={handleInput} value={colorInput}/> --> 
	<!-- Bind 2 ways instead of on:input and value -->
	<input type="text" bind:value={colorInput}/>
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