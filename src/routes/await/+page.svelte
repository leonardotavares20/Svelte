<script>
	let selectedBreed;
	let breeds = ['affenpinscher', 'appenzeller', 'basenji', 'shihtzu'];

	$: promise = getRandomBreed(selectedBreed)
	
	async function getRandomBreed(breed) {
		const response = await fetch(`https://dog.ceo/api/breed/${breed}/images/random`)
		const data = await response.json()
		return data
	}
</script>

<select bind:value={selectedBreed}>
	{#each breeds as breed (breed)}
		<option value={breed}>{breed}</option>
	{/each}
</select>

<h1>Selected Breed {selectedBreed}!</h1>

{#await promise}
	<p>...loading</p>
{:then {message}}
	<img src={message} alt="dog"/>
{:catch}
	<p>Oh No :D, svelte is soooo goooood</p>
{/await}



