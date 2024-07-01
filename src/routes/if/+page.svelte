<script>
	let conditionOne = true
	let conditionTwo = true

	function toggleConditionOne() {
		conditionOne = !conditionOne
	}

	function toggleConditionTwo() {
		conditionTwo = !conditionTwo
	}

	function check(conditionOne, conditionTwo) {
		return conditionOne || conditionTwo;
	}
</script>

<button on:click={toggleConditionOne}>Condition One: {conditionOne}</button>
<button on:click={toggleConditionTwo}>Condition Two: {conditionTwo}</button>

<hr/>

{#if conditionOne && conditionTwo}
	Condition One
{:else if !conditionOne && !conditionTwo}
	Oh No :D
{:else if check(conditionOne, conditionTwo)}
	Holaaaaa :P
{:else}
	Condition Two
{/if}

