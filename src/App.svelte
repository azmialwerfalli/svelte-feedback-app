<script>
	 let firstName = 'Azmi';
	 let lastName = 'Alfoghi'

	let color = 'blue'
	let showText = false
	let users  = [
		{
			id: '1',
			name: 'Azmi'
		},
		{
			id: '2',
			name: 'Ezzo'
		},
		{
			id: '3',
			name: 'Sarah'
		}
	]
	 $: name = firstName + ' ' + lastName
	 const toggle = () => {
		color = color === 'blue' ? 'red' : 'blue'
		showText = !showText
		users = [...users, {id: '4', name:'jalal'}]
	 }
</script>

<main>
	<h1 style="color: {color}">Hello {name}!</h1>
	{#if showText}
	<p>Some text Some text Some text Some text Some text .</p>
	{/if}
	<button on:click={toggle}>Click</button>
	{#each users as user (user.id)}
		<h3>{user.id}: {user.name}</h3>
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
		color: #ff3e00;
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