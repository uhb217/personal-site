<script>
	import { onMount } from 'svelte';

	let darkMode = false;

	function toggleDarkMode() {
		darkMode = !darkMode;
		document.documentElement.classList.toggle('dark', darkMode);
		localStorage.setItem('darkMode', darkMode);
	}

	onMount(() => {
		const saved = localStorage.getItem('darkMode');
		if (saved !== null) {
			darkMode = saved === 'true';
		} else {
			darkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
		}
		document.documentElement.classList.toggle('dark', darkMode);
	});
</script>

<main>
	<header>
		<nav>
			<a href="https://github.com/uhb217" target="_blank" rel="noopener noreferrer" class="github-link">
				<svg class="github-icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
					<path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
				</svg>
				<span>GitHub</span>
			</a>
			<button class="theme-toggle" on:click={toggleDarkMode} aria-label={darkMode ? 'Switch to light mode' : 'Switch to dark mode'}>
				{#if darkMode}
					<svg class="sun-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
						<circle cx="12" cy="12" r="5"/>
						<line x1="12" y1="1" x2="12" y2="3"/>
						<line x1="12" y1="21" x2="12" y2="23"/>
						<line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/>
						<line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/>
						<line x1="1" y1="12" x2="3" y2="12"/>
						<line x1="21" y1="12" x2="23" y2="12"/>
						<line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/>
						<line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/>
					</svg>
				{:else}
					<svg class="moon-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
						<path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
					</svg>
				{/if}
			</button>
		</nav>
	</header>

	<section class="hero">
		<h1>Hi, I'm <span class="name">Your Name</span></h1>
		<p class="tagline">Welcome to my personal website</p>
	</section>

	<section class="about">
		<h2>About Me</h2>
		<div class="about-content">
			<p class="placeholder">
				This is a placeholder for my about me section. I'll write something about myself here — 
				what I do, what I'm interested in, my background, and what I'm currently working on.
			</p>
			<p class="placeholder">
				Feel free to replace this text with your actual bio, skills, experience, or anything else 
				you'd like visitors to know about you.
			</p>
		</div>
	</section>

	<footer>
		<p>Built with Svelte • <a href="https://github.com/uhb217" target="_blank" rel="noopener noreferrer">View on GitHub</a></p>
	</footer>
</main>

<style>
	:global(:root) {
		--bg: #ffffff;
		--text: #1f2937;
		--text-muted: #6b7280;
		--accent: #2563eb;
		--accent-hover: #1d4ed8;
		--border: #e5e7eb;
		--card-bg: #f9fafb;
		--code-bg: #f3f4f6;
		--shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
		--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
	}

	:global(.dark) {
		--bg: #111827;
		--text: #f9fafb;
		--text-muted: #9ca3af;
		--accent: #60a5fa;
		--accent-hover: #93c5fd;
		--border: #374151;
		--card-bg: #1f2937;
		--code-bg: #1f2937;
		--shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.3), 0 2px 4px -2px rgba(0, 0, 0, 0.2);
		--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.4), 0 4px 6px -4px rgba(0, 0, 0, 0.3);
	}

	:global(*) {
		box-sizing: border-box;
	}

	:global(body) {
		margin: 0;
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
		background-color: var(--bg);
		color: var(--text);
		line-height: 1.6;
		transition: background-color 0.3s ease, color 0.3s ease;
		min-height: 100vh;
	}

	main {
		max-width: 800px;
		margin: 0 auto;
		padding: 2rem 1.5rem;
		min-height: 100vh;
		display: flex;
		flex-direction: column;
	}

	header {
		padding: 1rem 0;
	}

	nav {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.github-link {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		color: var(--text);
		text-decoration: none;
		font-weight: 500;
		padding: 0.5rem 1rem;
		border-radius: 8px;
		background-color: var(--card-bg);
		border: 1px solid var(--border);
		transition: all 0.2s ease;
	}

	.github-link:hover {
		color: var(--accent);
		border-color: var(--accent);
		transform: translateY(-1px);
		box-shadow: var(--shadow);
	}

	.github-icon {
		width: 20px;
		height: 20px;
		flex-shrink: 0;
	}

	.theme-toggle {
		background: var(--card-bg);
		border: 1px solid var(--border);
		border-radius: 50%;
		width: 44px;
		height: 44px;
		display: flex;
		align-items: center;
		justify-content: center;
		cursor: pointer;
		color: var(--text);
		transition: all 0.2s ease;
	}

	.theme-toggle:hover {
		background: var(--accent-bg);
		border-color: var(--accent);
		color: var(--accent);
		transform: scale(1.05);
	}

	.theme-toggle:focus-visible {
		outline: 2px solid var(--accent);
		outline-offset: 2px;
	}

	.sun-icon,
	.moon-icon {
		width: 22px;
		height: 22px;
	}

	.hero {
		flex: 1;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		text-align: center;
		padding: 3rem 0;
	}

	.hero h1 {
		font-size: clamp(2.5rem, 6vw, 4rem);
		font-weight: 700;
		margin: 0 0 1rem;
		line-height: 1.1;
		letter-spacing: -0.02em;
	}

	.name {
		color: var(--accent);
	}

	.tagline {
		font-size: clamp(1.1rem, 2.5vw, 1.375rem);
		color: var(--text-muted);
		margin: 0;
		max-width: 600px;
	}

	.about {
		padding: 2rem 0;
	}

	.about h2 {
		font-size: 1.75rem;
		font-weight: 600;
		margin: 0 0 1.5rem;
		color: var(--text);
	}

	.about-content {
		background: var(--card-bg);
		border: 1px solid var(--border);
		border-radius: 12px;
		padding: 2rem;
	}

	.placeholder {
		margin: 0 0 1rem;
		color: var(--text-muted);
		font-size: 1.05rem;
		line-height: 1.7;
	}

	.placeholder:last-child {
		margin-bottom: 0;
	}

	footer {
		padding: 2rem 0 1rem;
		text-align: center;
		border-top: 1px solid var(--border);
		margin-top: auto;
	}

	footer p {
		margin: 0;
		color: var(--text-muted);
		font-size: 0.9rem;
	}

	footer a {
		color: var(--accent);
		text-decoration: none;
	}

	footer a:hover {
		text-decoration: underline;
	}

	@media (max-width: 640px) {
		main {
			padding: 1.5rem 1rem;
		}

		.about-content {
			padding: 1.5rem;
		}
	}
</style>