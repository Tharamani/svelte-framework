<script>
	let firstname = 'thara';
	let lastname = 'm p';

	$: name = firstname + ' ' + lastname // reactive values
	let colorInput = 'red'

	// changing styles
	let color = 'red'

	// conditions if/else
	let showText = false

	//loops
	let users = [{id:1, name:'John'}, {id:2, name:'Mary'}, {id:3, name:'Eric'}]

	// named functions
	const toggle = () => {
		color = color === 'red' ? 'blue'  : 'red'
		colorInput = colorInput === 'red' ? 'blue'  : 'red'
		showText = !showText
		// colorInput = 'blue'
		
		// add new user 
		users = [...users, {id:4, name:'Jen'}]
	}

	const handleInput = (e) => {
		colorInput = e.target.value
	}

	
</script>

<main>
	<h1 style='color:{color}'>Hello {name}!</h1>

	{#if showText}
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.{colorInput}</p>
	{:else} <p>{color} : {colorInput}</p>
	{/if}

	<!-- <button on:click={() => {color = 'purple'}}>Click</button> -->
	<button on:click={toggle}>Click</button> 
	<input type="text" on:input={handleInput} value={colorInput}/>

	{#each users as user }
		<h2>{user.id} : {user.name}</h2>
	{/each}

	
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