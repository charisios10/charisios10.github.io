<script>
	import { page } from '$app/stores';
</script>

<nav>
	<ul>
		<li class:active={$page.url.pathname === '/'}>
			<a href="/">Home</a>
		</li>
		<li class:active={$page.url.pathname === '/projects'}>
			<a href="/projects">Projects</a>
		</li>
		<li class:active={$page.url.pathname === '/contact'}>
			<a href="/contact">Contact</a>
		</li>
	</ul>
</nav>

<style>
	nav {
		background-color: rgba(255, 255, 255, 0.1);
		padding: 1rem;
	}

	ul {
		list-style-type: none;
		padding: 0;
		display: flex;
		justify-content: center;
	}

	li {
		margin: 0 1rem;
	}

	a {
		color: #ffffff;
		text-decoration: none;
		font-weight: bold;
		transition: color 0.3s ease;
	}

	a:hover {
		color: #00ffff;
	}

	.active a {
		color: #00ffff;
	}
</style>
