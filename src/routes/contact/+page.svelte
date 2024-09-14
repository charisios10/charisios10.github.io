<script>
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>Charisios - Contact</title>
</svelte:head>

<div class="container" in:fly={{ y: 50, duration: 500 }}>
	<h1>Contact Me</h1>
	<form action="https://formsubmit.co/info@charisios.com" method="POST">
		<div class="form-group">
			<label for="name">Name</label>
			<input type="text" name="name" id="name" required />
		</div>
		<div class="form-group">
			<label for="email">Email</label>
			<input type="email" name="email" id="email" required />
		</div>
		<div class="form-group">
			<label for="message">Message</label>
			<textarea name="message" id="message" rows="5" required></textarea>
		</div>
		<button type="submit">Send Message</button>
	</form>
</div>

<style>
	.container {
		max-width: 600px;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.5rem;
		margin-bottom: 2rem;
		color: #00ffff;
		text-align: center;
	}

	form {
		background-color: rgba(255, 255, 255, 0.1);
		padding: 2rem;
		border-radius: 8px;
	}

	.form-group {
		margin-bottom: 1.5rem;
	}

	label {
		display: block;
		margin-bottom: 0.5rem;
		color: #00ffff;
	}

	input,
	textarea {
		width: 100%;
		padding: 0.5rem;
		background-color: rgba(255, 255, 255, 0.2);
		border: none;
		border-radius: 4px;
		color: #ffffff;
	}

	button {
		display: block;
		width: 100%;
		padding: 0.75rem;
		background-color: #00ffff;
		color: #0a0a2a;
		border: none;
		border-radius: 4px;
		font-size: 1rem;
		cursor: pointer;
		transition: background-color 0.3s ease;
	}

	button:hover {
		background-color: #00cccc;
	}
</style>
