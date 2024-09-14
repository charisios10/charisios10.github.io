<script>
	import { fly } from 'svelte/transition';
	import { Github, Linkedin, Twitter, Code, ExternalLink } from 'lucide-svelte';

	const socialLinks = [
		{ icon: Github, url: 'https://github.com/charisios10', label: 'GitHub' },
		{ icon: Linkedin, url: 'https://www.linkedin.com/in/charisios-charisiadis', label: 'LinkedIn' },
		{ icon: Twitter, url: 'https://twitter.com/Charisios10', label: 'Twitter' }
	];

	const pinnedProjects = [
		{
			name: 'Charisios Portofolio',
			description: 'My own portofolio!',
			url: 'https://github.com/charisios10/charisios10.github.io'
		},
		{
			name: 'Scp Site Roleplay Guide',
			description: 'A guide for players to understand and learn the game!',
			url: 'https://github.com/charisios10/scp-site-roleplay'
		},
		{
			name: 'Small Solar System',
			description: 'One of my first ever projects!',
			url: 'https://github.com/charisios10/small-solar-system'
		},
		{
			name: 'Tetris Game',
			description: 'A small tetris game that you can play!',
			url: 'https://github.com/charisios10/tetris-game'
		}
	];
</script>

<svelte:head>
	<title>Charisios Portofolio</title>
</svelte:head>

<div class="container" in:fly={{ y: 50, duration: 500 }}>
	<h1>Charisios Charisiadis</h1>
	<div class="avatar">
		<img src="https://avatars.githubusercontent.com/u/119067361?v=4" alt="Charisios Charisiadis" />
	</div>
	<p class="tagline">Exploring the universe of code and creativity</p>

	<section class="about">
		<h2>About Me</h2>
		<p>
			Hello! I'm Charisios, a passionate developer with a love for creating innovative solutions.
			With a background in Web Developement, I specialize in Server Administration. When I'm not
			coding, you can find me playing games or maybe traveling!.
		</p>
	</section>

	<section class="projects">
		<h2>Featured Projects</h2>
		<div class="project-grid">
			{#each pinnedProjects as project}
				<div class="project-card">
					<h3>{project.name}</h3>
					<p>{project.description}</p>
					<a href={project.url} target="_blank" rel="noopener noreferrer">
						<Code size={16} /> View Project
					</a>
				</div>
			{/each}
		</div>
	</section>

	<section class="social-links">
		<h2>Connect with Me</h2>
		<div class="links">
			{#each socialLinks as { icon: Icon, url, label }}
				<a href={url} target="_blank" rel="noopener noreferrer" aria-label={label}>
					<Icon size={24} />
				</a>
			{/each}
		</div>
	</section>
</div>

<style>
	.container {
		text-align: center;
		padding: 2rem;
		max-width: 800px;
		margin: 0 auto;
	}

	h1 {
		font-size: 3rem;
		margin-bottom: 1rem;
		color: #00ffff;
	}

	h2 {
		font-size: 2rem;
		color: #00cccc;
		margin-top: 2rem;
		margin-bottom: 1rem;
	}

	.avatar {
		width: 150px;
		height: 150px;
		border-radius: 50%;
		overflow: hidden;
		margin: 0 auto 1rem;
		border: 3px solid #00ffff;
	}

	.avatar img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.tagline {
		font-size: 1.2rem;
		color: #b3e0e0;
		margin-bottom: 2rem;
	}

	.about,
	.projects,
	.social-links {
		background-color: rgba(255, 255, 255, 0.1);
		padding: 1.5rem;
		border-radius: 8px;
		margin-bottom: 2rem;
	}

	.about p {
		text-align: left;
		line-height: 1.6;
	}

	.project-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 1rem;
	}

	.project-card {
		background-color: rgba(255, 255, 255, 0.05);
		padding: 1rem;
		border-radius: 8px;
		text-align: left;
	}

	.project-card h3 {
		color: #00ffff;
		margin-bottom: 0.5rem;
	}

	.project-card p {
		margin-bottom: 1rem;
	}

	.project-card a {
		display: inline-flex;
		align-items: center;
		color: #00ffff;
		text-decoration: none;
		transition: color 0.3s ease;
	}

	.project-card a:hover {
		color: #ffffff;
	}

	.social-links .links {
		display: flex;
		justify-content: center;
		gap: 1rem;
	}

	.social-links a {
		color: #00ffff;
		transition: color 0.3s ease;
	}

	.social-links a:hover {
		color: #ffffff;
	}
</style>
