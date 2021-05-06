<script>
	let user = "hassan";

	let todos = [
		{
			name: "wash dishes",
			dateCreated: "9:00 AM 6 May 2021",
			completed: false,
			user: "hassan",
			id: "1",
		},
		{
			name: "clean car",
			dateCreated: "8:10 AM 6 May 2021",
			completed: false,
			user: "hassan",
			id: "2",
		},
		{
			name: "clean carpet",
			dateCreated: "6:21 AM 6 May 2021",
			completed: true,
			user: "hassan",
			id: "3",
		},
		{
			name: "fix watch",
			dateCreated: "4:32 AM 6 May 2021",
			completed: false,
			user: "hassan",
			id: "4",
		},
		{
			name: "clean monitor",
			dateCreated: "5:44 AM 6 May 2021",
			completed: false,
			user: "hassan",
			id: "5",
		},
	];

	// cR ; conditionalRendering
	const cR = (condition, ifTrue, ifFalse = "") =>
		condition ? ifTrue : ifFalse;

	const filterOut = (id) => (todos = todos.filter((item) => item.id !== id));
	const handleClick = (id) => filterOut(id);
</script>

<link
	rel="stylesheet"
	href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
	integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
	crossorigin="anonymous"
/>

<main>
	<h1>User is {user}</h1>

	<table class="table">
		{#each todos as todo}
			<tr class={cR(todo.completed, "completed")}>
				<td>{todo.name}</td>
				<td>{todo.dateCreated}</td>
				<td>{todo.completed}</td>
				<td>
					{#if !todo.completed}
						<button
							class="btn btn-danger"
							on:click={() => handleClick(todo.id)}>X</button
						>
					{/if}
				</td>
			</tr>
		{/each}
	</table>
</main>

<style>
	.completed {
		background-color: #00ff00;
	}
</style>
