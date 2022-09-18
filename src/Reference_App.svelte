<script>
	// export let name;
	let firstName = "ken";
	let LastName = "Furukawa";
	let primaryColor = 'blue';
	let showText = false;
	let users = [
		{
			id: '1',
			name: 'John'
		},
		{
			id: '2',
			name: 'Sara'
		},
		{
			id: '3',
			name: 'Terry'
		}
	]

	$: name = firstName + ' ' + LastName;

	const toggle = () => {
		primaryColor = primaryColor === 'blue' ? 'purple' : 'blue';
		showText = !showText;
		users = [...users, {id: users.length++, name: 'Lion'}]
	}
</script>

<main>
	<h1 style="color: {primaryColor};">Hello {name}!</h1>
	<button on:click={toggle}>Click</button>
	{#if showText}
		<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
		{:else}
			<p>No text here.</p>
	{/if}

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
		/* color: {primaryColor}; */
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 500;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>