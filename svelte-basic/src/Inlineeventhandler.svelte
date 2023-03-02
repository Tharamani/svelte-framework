<script>
	let people = [
    { name: 'yoshi', beltColour: 'black', age: 25, id: 1 },
    { name: 'mario', beltColour: 'orange', age: 45, id: 2 },
    { name: 'luigi', beltColour: 'brown', age: 35, id: 3 }
  ];

  const handleClick = (id) => {
    console.log(id)
    people = people.filter(person => person.id !== id)
  }
</script>

<main>

    {#each  people as person (person.id) }
        <div>
            <h4>{person.name}</h4>
            <p>{person.age} years old, {person.beltColour} belt.</p>
            <!-- handleClick() is called for each person element to overcome this use inline event handler-->
            <!-- <button on:click={handleClick(person.id)}>Delete</button> -->
             <!-- Inline event handler , handler is called only when event occurs-->
             <button on:click={() => {handleClick(person.id)}}>Delete</button>
        </div>
        {:else} <p>No people to dispaly</p>
    {/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>