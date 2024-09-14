<script>
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';

	let repos = [];

	onMount(async () => {
		const response = await fetch('https://api.github.com/users/charisios10/repos');
		const data = await response.json();
		repos = data.map((repo) => ({
			name: repo.name,
			description: repo.description,
			url: repo.html_url,
			stars: repo.stargazers_count,
			language: repo.language
		}));
	});
</script>

<svelte:head>
	<title>Charisios - Projects</title>
</svelte:head>

<div class="container" in:fly={{ y: 50, duration: 500 }}>
	<h1>My Projects</h1>
	<div class="projects">
		{#each repos as repo}
			<div class="project">
				<h2>{repo.name}</h2>
				<p>{repo.description || 'No description available'}</p>
				<p>Language: {repo.language || 'Not specified'}</p>
				<p>Stars: {repo.stars}</p>
				<a href={repo.url} target="_blank" rel="noopener noreferrer">View on GitHub</a>
			</div>
		{/each}
	</div>
</div>

<style>
	.container {
		text-align: center;
	}

	h1 {
		font-size: 2.5rem;
		margin-bottom: 2rem;
		color: #00ffff;
	}

	.projects {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 2rem;
	}

	.project {
		background-color: rgba(255, 255, 255, 0.1);
		padding: 1.5rem;
		border-radius: 8px;
		transition: transform 0.3s ease;
	}

	.project:hover {
		transform: translateY(-5px);
	}

	h2 {
		font-size: 1.5rem;
		margin-bottom: 0.5rem;
		color: #00ffff;
	}

	a {
		display: inline-block;
		margin-top: 1rem;
		padding: 0.5rem 1rem;
		background-color: #00ffff;
		color: #0a0a2a;
		text-decoration: none;
		border-radius: 4px;
		transition: background-color 0.3s ease;
	}

	a:hover {
		background-color: #00cccc;
	}
</style>
