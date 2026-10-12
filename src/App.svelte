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

	const projects = [
		{
			name: 'PlayerTracker',
			description: 'A cool client-side mod that lets you track players with a compass 🧭',
			language: 'Java',
			url: 'https://github.com/uhb217/PlayerTracker',
			stars: 2,
			updated: '2026-09-15'
		},
		{
			name: 'Airdrop',
			description: 'File sharing utility built with Python',
			language: 'Python',
			url: 'https://github.com/uhb217/Airdrop',
			stars: 0,
			updated: '2025-08-02'
		},
		{
			name: 'chess0.2',
			description: 'Chess engine and GUI implementation in Java',
			language: 'Java',
			url: 'https://github.com/uhb217/chess0.2',
			stars: 0,
			updated: '2025-09-30'
		}
	];

	const skills = ['Kotlin', 'Java', 'Python', 'JavaScript', 'Android', 'Svelte'];
</script>

<main>
	<header class="top-nav">
		<div class="nav-content">
			<a href="/" class="wordmark" aria-label="Home">uhb217</a>
			<nav class="nav-links">
				<a href="#about" class="nav-link">About</a>
				<a href="#projects" class="nav-link">Projects</a>
				<a href="#skills" class="nav-link">Skills</a>
			</nav>
			<div class="nav-actions">
				<a href="https://github.com/uhb217" target="_blank" rel="noopener noreferrer" class="github-link" aria-label="View GitHub profile">
					<svg class="github-icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
						<path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
					</svg>
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
			</div>
		</div>
	</header>

	<section class="hero-band" aria-labelledby="hero-title">
		<div class="hero-gradient" aria-hidden="true"></div>
		<div class="hero-content">
			<div class="hero-text">
				<h1 id="hero-title" class="display-mega">Hi, I'm <span class="name">uhb217</span></h1>
				<p class="hero-subhead body-md">18-year-old hobbyist developer building Android apps and Python tools</p>
				<div class="hero-cta-group">
					<a href="https://github.com/uhb217" target="_blank" rel="noopener noreferrer" class="button-primary">
						<svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18" aria-hidden="true">
							<path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
						</svg>
						View GitHub
					</a>
				</div>
			</div>
			<div class="device-mockup" aria-hidden="true">
				<div class="mockup-frame">
					<div class="mockup-screen">
						<div class="mockup-code">
												<pre><code>{`fun main() {
						    println("Building cool stuff...")
						}`}</code></pre>
											</div>
					</div>
					<div class="mockup-phone">
						<div class="mockup-phone-screen">
							<div class="phone-app">
								<div class="phone-header">PlayerTracker</div>
								<div class="phone-compass">🧭</div>
								<div class="phone-status">Tracking...</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section id="about" class="section about-section" aria-labelledby="about-title">
		<div class="container">
			<div class="about-grid">
				<div class="about-profile">
					<img src="https://avatars.githubusercontent.com/u/120917778?v=4&size=200" alt="" class="profile-avatar" loading="lazy"/>
					<div class="profile-badges">
						<span class="badge-pill">18 years old</span>
						<span class="badge-pill">Hobbyist</span>
						<span class="badge-pill">Open Source</span>
					</div>
				</div>
				<div class="about-content">
					<h2 id="about-title" class="display-lg">About Me</h2>
					<div class="about-text body-md">
						<p>I'm an 18-year-old developer who codes as a hobby. My main languages are <strong>Kotlin</strong> and <strong>Java</strong>, but I also work with <strong>Python</strong> and <strong>JavaScript</strong> for various projects.</p>
						<p>I enjoy building <strong>Android applications</strong> and creating <strong>small tools with Python</strong> to solve problems or automate tasks. Most of my work is open source on GitHub.</p>
						<p>When I'm not coding, I'm probably exploring new libraries, experimenting with different architectures, or playing chess (hence the chess engine project).</p>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section id="skills" class="section skills-section surface-soft" aria-labelledby="skills-title">
		<div class="container">
			<h2 id="skills-title" class="display-md section-title">Skills & Technologies</h2>
			<div class="skills-grid">
				{#each skills as skill}
					<span class="skill-tag">{skill}</span>
				{/each}
			</div>
		</div>
	</section>

	<section id="projects" class="section projects-section" aria-labelledby="projects-title">
		<div class="container">
			<div class="section-header">
				<h2 id="projects-title" class="display-lg">Featured Projects</h2>
				<a href="https://github.com/uhb217?tab=repositories" target="_blank" rel="noopener noreferrer" class="button-tertiary">
					View all repositories
					<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
						<line x1="5" y1="12" x2="19" y2="12"/>
						<polyline points="12 5 19 12 12 19"/>
					</svg>
				</a>
			</div>
			<div class="projects-grid">
				{#each projects as project}
					<article class="project-card feature-card">
						<div class="project-header">
							<h3 class="project-name title-md">{project.name}</h3>
							<span class="project-language badge-pill">{project.language}</span>
						</div>
						<p class="project-description body-md">{project.description}</p>
						<div class="project-meta">
							<span class="project-stars">
								<svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
									<path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
								</svg>
								{project.stars}
							</span>
							<span class="project-updated">Updated {project.updated}</span>
						</div>
						<a href={project.url} target="_blank" rel="noopener noreferrer" class="project-link button-tertiary">
							View code
							<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
								<line x1="5" y1="12" x2="19" y2="12"/>
								<polyline points="12 5 19 12 12 19"/>
							</svg>
						</a>
					</article>
				{/each}
			</div>
		</div>
	</section>

	<section class="section cta-band" aria-labelledby="cta-title">
		<div class="container">
			<h2 id="cta-title" class="display-lg cta-title">Want to collaborate or say hi?</h2>
			<p class="cta-subhead body-md">I'm always open to interesting projects and conversations.</p>
			<a href="https://github.com/uhb217" target="_blank" rel="noopener noreferrer" class="button-primary">Get in touch on GitHub</a>
		</div>
	</section>

	<footer class="footer-light">
		<div class="container">
			<div class="footer-grid">
				<div class="footer-brand">
					<p class="footer-wordmark">uhb217</p>
					<p class="footer-tagline body-sm">Building for fun since 2020</p>
				</div>
				<nav class="footer-nav" aria-label="Footer navigation">
					<div class="footer-column">
						<h4 class="caption-uppercase">Projects</h4>
						<ul>
							<li><a href="https://github.com/uhb217/PlayerTracker" target="_blank" rel="noopener noreferrer" class="footer-link">PlayerTracker</a></li>
							<li><a href="https://github.com/uhb217/Airdrop" target="_blank" rel="noopener noreferrer" class="footer-link">Airdrop</a></li>
							<li><a href="https://github.com/uhb217/chess0.2" target="_blank" rel="noopener noreferrer" class="footer-link">chess0.2</a></li>
						</ul>
					</div>
					<div class="footer-column">
						<h4 class="caption-uppercase">Connect</h4>
						<ul>
							<li><a href="https://github.com/uhb217" target="_blank" rel="noopener noreferrer" class="footer-link">GitHub</a></li>
						</ul>
					</div>
				</nav>
			</div>
			<div class="footer-bottom">
				<p class="copyright body-sm">Built with Svelte · Deployed on GitHub Pages</p>
			</div>
		</div>
	</footer>
</main>

<style>
	:global(:root) {
		/* Colors - Expo Design System */
		--color-primary: #000000;
		--color-primary-active: #1a1a1a;
		--color-text-link: #0d74ce;
		--color-text-link-secondary: #476cff;
		--color-ink: #171717;
		--color-body: #60646c;
		--color-body-strong: #171717;
		--color-muted: #999999;
		--color-muted-soft: #cccccc;
		--color-hairline: #f0f0f3;
		--color-hairline-soft: #f5f5f7;
		--color-hairline-strong: #dcdee0;
		--color-canvas: #ffffff;
		--color-canvas-soft: #fafafa;
		--color-surface-card: #ffffff;
		--color-surface-strong: #f0f0f3;
		--color-surface-dark: #171717;
		--color-surface-dark-elevated: #1a1a1a;
		--color-on-primary: #ffffff;
		--color-on-dark: #ffffff;
		--color-on-dark-soft: #b0b4ba;
		--color-gradient-sky-light: #cfe7ff;
		--color-gradient-sky-mid: #a8c8e8;
		--color-accent-warning: #ab6400;
		--color-accent-preview: #8145b5;
		--color-accent-link-bright: #47c2ff;
		--color-semantic-error: #eb8e90;
		--color-semantic-success: #16a34a;

		/* Dark mode overrides */
		--color-canvas-dark: #0a0a0a;
		--color-canvas-soft-dark: #111111;
		--color-surface-card-dark: #171717;
		--color-surface-strong-dark: #1f1f1f;
		--color-hairline-dark: #2a2a2a;
		--color-hairline-strong-dark: #333333;
		--color-ink-dark: #f5f5f5;
		--color-body-dark: #b0b4ba;
		--color-muted-dark: #777777;
	}

	:global(.dark) {
		--color-canvas: var(--color-canvas-dark);
		--color-canvas-soft: var(--color-canvas-soft-dark);
		--color-surface-card: var(--color-surface-card-dark);
		--color-surface-strong: var(--color-surface-strong-dark);
		--color-hairline: var(--color-hairline-dark);
		--color-hairline-strong: var(--color-hairline-strong-dark);
		--color-ink: var(--color-ink-dark);
		--color-body: var(--color-body-dark);
		--color-muted: var(--color-muted-dark);
	}

	/* Typography - Inter + JetBrains Mono */
	:global(*) {
		box-sizing: border-box;
	}

	:global(body) {
		margin: 0;
		font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
		background-color: var(--color-canvas);
		color: var(--color-ink);
		line-height: 1.5;
		transition: background-color 0.3s ease, color 0.3s ease;
		min-height: 100vh;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	/* Font faces loaded via index.html preconnect */

	/* Typography utility classes */
	.display-mega {
		font-family: 'Inter', sans-serif;
		font-size: clamp(32px, 6vw, 64px);
		font-weight: 600;
		line-height: 1.05;
		letter-spacing: -0.03em;
	}

	.display-lg {
		font-family: 'Inter', sans-serif;
		font-size: clamp(24px, 4vw, 36px);
		font-weight: 600;
		line-height: 1.15;
		letter-spacing: -0.03em;
	}

	.display-md {
		font-family: 'Inter', sans-serif;
		font-size: clamp(22px, 3vw, 28px);
		font-weight: 600;
		line-height: 1.2;
		letter-spacing: -0.03em;
	}

	.title-md {
		font-family: 'Inter', sans-serif;
		font-size: 18px;
		font-weight: 600;
		line-height: 1.4;
		letter-spacing: 0;
	}

	.body-md {
		font-family: 'Inter', sans-serif;
		font-size: 16px;
		font-weight: 400;
		line-height: 1.5;
		letter-spacing: 0;
	}

	.body-sm {
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 400;
		line-height: 1.5;
		letter-spacing: 0;
	}

	.caption-uppercase {
		font-family: 'Inter', sans-serif;
		font-size: 11px;
		font-weight: 600;
		line-height: 1.4;
		letter-spacing: 0.08em;
		text-transform: uppercase;
	}

	.nav-link {
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 500;
		line-height: 1.4;
		letter-spacing: 0;
	}

	/* Spacing */
	.section {
		padding: 96px 0;
	}

	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 24px;
	}

	/* Layout */
	main {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
	}

	/* Top Navigation */
	.top-nav {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		height: 64px;
		background-color: var(--color-canvas);
		border-bottom: 1px solid var(--color-hairline);
		z-index: 100;
		transition: background-color 0.3s ease, border-color 0.3s ease;
	}

	.nav-content {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 24px;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 24px;
	}

	.wordmark {
		font-family: 'Inter', sans-serif;
		font-size: 18px;
		font-weight: 600;
		color: var(--color-ink);
		text-decoration: none;
		letter-spacing: -0.02em;
	}

	.nav-links {
		display: flex;
		gap: 32px;
	}

	.nav-link {
		color: var(--color-body);
		text-decoration: none;
		transition: color 0.2s ease;
	}

	.nav-link:hover {
		color: var(--color-ink);
	}

	.nav-actions {
		display: flex;
		align-items: center;
		gap: 12px;
	}

	.github-link {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 40px;
		height: 40px;
		border-radius: 8px;
		background-color: var(--color-surface-strong);
		color: var(--color-ink);
		text-decoration: none;
		transition: all 0.2s ease;
		border: 1px solid var(--color-hairline-strong);
	}

	.github-link:hover {
		background-color: var(--color-primary);
		color: var(--color-on-primary);
		border-color: var(--color-primary);
	}

	.github-icon {
		width: 20px;
		height: 20px;
	}

	.theme-toggle {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 44px;
		height: 44px;
		border-radius: 50%;
		background-color: var(--color-surface-strong);
		border: 1px solid var(--color-hairline-strong);
		color: var(--color-ink);
		cursor: pointer;
		transition: all 0.2s ease;
	}

	.theme-toggle:hover {
		background-color: var(--color-primary);
		border-color: var(--color-primary);
		color: var(--color-on-primary);
		transform: scale(1.05);
	}

	.theme-toggle:focus-visible {
		outline: 2px solid var(--color-primary);
		outline-offset: 2px;
	}

	.sun-icon,
	.moon-icon {
		width: 22px;
		height: 22px;
	}

	/* Hero Band */
	.hero-band {
		position: relative;
		padding: 120px 0 96px;
		background-color: var(--color-canvas);
		overflow: hidden;
		margin-top: 64px;
	}

	.hero-gradient {
		position: absolute;
		top: 0;
		left: 50%;
		transform: translateX(-50%);
		width: 100%;
		max-width: 1200px;
		height: 100%;
		background: radial-gradient(ellipse 80% 50% at 50% 0%, var(--color-gradient-sky-light) 0%, transparent 70%);
		opacity: 0.6;
		pointer-events: none;
	}

	:global(.dark) .hero-gradient {
		background: radial-gradient(ellipse 80% 50% at 50% 0%, rgba(168, 200, 232, 0.15) 0%, transparent 70%);
	}

	.hero-content {
		position: relative;
		z-index: 1;
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 24px;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 48px;
		align-items: start;
	}

	.hero-text {
		text-align: left;
		padding-top: 24px;
	}

	.hero-text .name {
		color: var(--color-primary);
	}

	.hero-subhead {
		color: var(--color-body);
		margin: 16px 0 32px;
		max-width: 480px;
	}

	.hero-cta-group {
		display: flex;
		gap: 16px;
		flex-wrap: wrap;
	}

	/* Buttons */
	.button-primary {
		display: inline-flex;
		align-items: center;
		gap: 8px;
		background-color: var(--color-primary);
		color: var(--color-on-primary);
		padding: 10px 18px;
		border-radius: 8px;
		text-decoration: none;
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 500;
		line-height: 1.0;
		height: 40px;
		border: none;
		cursor: pointer;
		transition: background-color 0.2s ease, transform 0.1s ease;
	}

	.button-primary:hover {
		background-color: var(--color-primary-active);
		transform: translateY(-1px);
	}

	.button-primary:active {
		transform: translateY(0);
	}

	.button-primary:focus-visible {
		outline: 2px solid var(--color-primary);
		outline-offset: 2px;
	}

	.button-tertiary {
		display: inline-flex;
		align-items: center;
		gap: 6px;
		background-color: transparent;
		color: var(--color-text-link);
		padding: 8px 0;
		text-decoration: none;
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 500;
		line-height: 1.0;
		border: none;
		cursor: pointer;
		transition: color 0.2s ease;
	}

	.button-tertiary:hover {
		color: var(--color-text-link-secondary);
		text-decoration: underline;
	}

	.button-tertiary:focus-visible {
		outline: 2px solid var(--color-text-link);
		outline-offset: 2px;
		border-radius: 4px;
	}

	/* Device Mockup */
	.device-mockup {
		display: flex;
		justify-content: center;
		align-items: flex-end;
	}

	.mockup-frame {
		position: relative;
		width: 100%;
		max-width: 480px;
	}

	.mockup-screen {
		background-color: var(--color-surface-dark);
		border-radius: 16px;
		padding: 24px;
		box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3), 0 0 0 1px rgba(255, 255, 255, 0.05);
		margin-bottom: -60px;
		z-index: 2;
	}

	.mockup-code {
		font-family: 'JetBrains Mono', monospace;
		font-size: 14px;
		line-height: 1.6;
		color: var(--color-on-dark);
		white-space: pre-wrap;
	}

	.mockup-phone {
		position: relative;
		width: 160px;
		height: 320px;
		background: linear-gradient(180deg, #1a1a1a 0%, #0d0d0d 100%);
		border-radius: 32px;
		padding: 8px;
		box-shadow: 0 25px 50px rgba(0, 0, 0, 0.4);
		z-index: 1;
		margin-left: -40px;
	}

	.mockup-phone-screen {
		width: 100%;
		height: 100%;
		background-color: var(--color-surface-dark);
		border-radius: 24px;
		overflow: hidden;
		display: flex;
		flex-direction: column;
	}

	.phone-app {
		padding: 20px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
		gap: 16px;
	}

	.phone-header {
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 600;
		color: var(--color-on-dark);
	}

	.phone-compass {
		font-size: 48px;
		line-height: 1;
	}

	.phone-status {
		font-family: 'Inter', sans-serif;
		font-size: 12px;
		color: var(--color-on-dark-soft);
	}

	/* Sections */
	.section {
		background-color: var(--color-canvas);
	}

	.surface-soft {
		background-color: var(--color-canvas-soft);
	}

	.section-header {
		display: flex;
		align-items: baseline;
		justify-content: space-between;
		gap: 24px;
		margin-bottom: 48px;
		flex-wrap: wrap;
	}

	.section-title {
		color: var(--color-ink);
		margin: 0;
	}

	/* About Section */
	.about-grid {
		display: grid;
		grid-template-columns: 280px 1fr;
		gap: 64px;
		align-items: start;
	}

	.about-profile {
		position: sticky;
		top: 120px;
	}

	.profile-avatar {
		width: 100%;
		max-width: 280px;
		aspect-ratio: 1;
		border-radius: 16px;
		border: 1px solid var(--color-hairline-strong);
		background-color: var(--color-surface-strong);
	}

	.profile-badges {
		display: flex;
		flex-wrap: wrap;
		gap: 8px;
		margin-top: 16px;
	}

	.badge-pill {
		display: inline-flex;
		background-color: var(--color-surface-strong);
		color: var(--color-ink);
		padding: 4px 10px;
		border-radius: 9999px;
		font-family: 'Inter', sans-serif;
		font-size: 11px;
		font-weight: 600;
		line-height: 1.4;
		letter-spacing: 0.08em;
		text-transform: uppercase;
		border: 1px solid var(--color-hairline);
	}

	.about-content {
		max-width: 720px;
	}

	.about-text {
		color: var(--color-body);
	}

	.about-text p {
		margin: 0 0 16px;
	}

	.about-text p:last-child {
		margin-bottom: 0;
	}

	.about-text strong {
		color: var(--color-ink);
		font-weight: 600;
	}

	/* Skills Section */
	.skills-grid {
		display: flex;
		flex-wrap: wrap;
		gap: 12px;
	}

	.skill-tag {
		display: inline-flex;
		align-items: center;
		background-color: var(--color-surface-card);
		color: var(--color-ink);
		padding: 8px 16px;
		border-radius: 8px;
		border: 1px solid var(--color-hairline-strong);
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 500;
		transition: all 0.2s ease;
	}

	.skill-tag:hover {
		border-color: var(--color-primary);
		color: var(--color-primary);
		transform: translateY(-1px);
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
	}

	/* Projects Section */
	.projects-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
		gap: 24px;
	}

	.project-card {
		display: flex;
		flex-direction: column;
		height: 100%;
		transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
	}

	.project-card:hover {
		transform: translateY(-4px);
		box-shadow: 0 12px 24px rgba(0, 0, 0, 0.08);
		border-color: var(--color-hairline-strong);
	}

	.project-header {
		display: flex;
		align-items: flex-start;
		justify-content: space-between;
		gap: 12px;
		margin-bottom: 12px;
	}

	.project-name {
		color: var(--color-ink);
		margin: 0;
		flex: 1;
	}

	.project-language {
		flex-shrink: 0;
	}

	.project-description {
		color: var(--color-body);
		margin: 0 0 16px;
		flex: 1;
	}

	.project-meta {
		display: flex;
		align-items: center;
		gap: 16px;
		margin-bottom: 16px;
		font-family: 'Inter', sans-serif;
		font-size: 13px;
		color: var(--color-muted);
	}

	.project-stars {
		display: inline-flex;
		align-items: center;
		gap: 4px;
	}

	.project-link {
		margin-top: auto;
		align-self: flex-start;
	}

	/* CTA Band */
	.cta-band {
		background-color: var(--color-canvas);
		text-align: center;
		padding: 96px 0;
	}

	.cta-title {
		color: var(--color-ink);
		margin: 0 0 12px;
	}

	.cta-subhead {
		color: var(--color-body);
		margin: 0 0 24px;
		max-width: 600px;
		margin-left: auto;
		margin-right: auto;
	}

	/* Footer */
	.footer-light {
		background-color: var(--color-canvas);
		border-top: 1px solid var(--color-hairline);
		padding: 64px 0 32px;
		margin-top: auto;
	}

	.footer-grid {
		display: grid;
		grid-template-columns: 1fr 2fr;
		gap: 48px;
		margin-bottom: 48px;
	}

	.footer-wordmark {
		font-family: 'Inter', sans-serif;
		font-size: 18px;
		font-weight: 600;
		color: var(--color-ink);
		margin: 0 0 8px;
		letter-spacing: -0.02em;
	}

	.footer-tagline {
		color: var(--color-body);
		margin: 0;
	}

	.footer-nav {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 32px;
	}

	.footer-column h4 {
		margin: 0 0 12px;
		color: var(--color-muted);
	}

	.footer-column ul {
		list-style: none;
		padding: 0;
		margin: 0;
		display: flex;
		flex-direction: column;
		gap: 8px;
	}

	.footer-link {
		color: var(--color-body);
		text-decoration: none;
		font-family: 'Inter', sans-serif;
		font-size: 14px;
		font-weight: 400;
		line-height: 1.5;
		transition: color 0.2s ease;
	}

	.footer-link:hover {
		color: var(--color-ink);
		text-decoration: underline;
	}

	.footer-bottom {
		padding-top: 32px;
		border-top: 1px solid var(--color-hairline);
		text-align: center;
	}

	.copyright {
		color: var(--color-muted);
		margin: 0;
	}

	/* Responsive */
	@media (max-width: 1024px) {
		.hero-content {
			grid-template-columns: 1fr;
			gap: 48px;
			text-align: center;
		}

		.hero-text {
			padding-top: 0;
		}

		.hero-cta-group {
			justify-content: center;
		}

		.device-mockup {
			max-width: 480px;
			margin: 0 auto;
		}

		.about-grid {
			grid-template-columns: 1fr;
			gap: 32px;
		}

		.about-profile {
			position: static;
			max-width: 280px;
			margin: 0 auto;
		}

		.profile-badges {
			justify-content: center;
		}
	}

	@media (max-width: 768px) {
		.nav-links {
			display: none;
		}

		.top-nav {
			padding: 0 16px;
		}

		.nav-content {
			padding: 0 16px;
		}

		.container {
			padding: 0 16px;
		}

		.section {
			padding: 64px 0;
		}

		.hero-band {
			padding: 100px 0 64px;
		}

		.projects-grid {
			grid-template-columns: 1fr;
		}

		.footer-grid {
			grid-template-columns: 1fr;
			gap: 32px;
			text-align: center;
		}

		.footer-nav {
			grid-template-columns: 1fr;
			gap: 24px;
		}

		.mockup-phone {
			display: none;
		}
	}

	@media (max-width: 640px) {
		.hero-band {
			margin-top: 64px;
			padding: 80px 0 48px;
		}

		.mockup-screen {
			padding: 16px;
		}

		.mockup-code {
			font-size: 12px;
		}
	}

	/* Reduced motion */
	@media (prefers-reduced-motion: reduce) {
		*,
		*::before,
		*::after {
			animation-duration: 0.01ms !important;
			animation-iteration-count: 1 !important;
			transition-duration: 0.01ms !important;
			scroll-behavior: auto !important;
		}
	}

	/* Focus visible for keyboard navigation */
	:global(:focus-visible) {
		outline: 2px solid var(--color-primary);
		outline-offset: 2px;
	}
</style>