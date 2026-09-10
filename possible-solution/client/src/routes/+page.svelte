<script lang="ts">
	let menuOpen = false;
	let activeArea = 'All';

	const areas = ['All', 'People', 'Planet', 'Everyday life'];

	const innovations = [
		{
			title: 'Healthcare',
			kicker: 'Earlier answers',
			description: 'AI can spot patterns in scans and patient data, helping clinicians notice warning signs sooner.',
			tag: 'People',
			icon: '＋',
			color: 'coral'
		},
		{
			title: 'Education',
			kicker: 'Learning that adapts',
			description: 'Personalized practice gives each learner helpful hints and a pace that fits their needs.',
			tag: 'People',
			icon: '✦',
			color: 'sun'
		},
		{
			title: 'Agriculture',
			kicker: 'Smarter growing',
			description: 'Sensors and satellite images help farmers use water carefully and protect crops.',
			tag: 'Planet',
			icon: '⌁',
			color: 'mint'
		},
		{
			title: 'Transport',
			kicker: 'Moving together',
			description: 'AI predicts traffic, plans efficient routes, and supports safer journeys for everyone.',
			tag: 'Everyday life',
			icon: '↗',
			color: 'blue'
		},
		{
			title: 'Accessibility',
			kicker: 'More ways to connect',
			description: 'Live captions, image descriptions, and voice tools make digital spaces more welcoming.',
			tag: 'People',
			icon: '◌',
			color: 'lilac'
		}
	];

	$: visibleInnovations =
		activeArea === 'All' ? innovations : innovations.filter((innovation) => innovation.tag === activeArea);
</script>

<svelte:head>
	<title>Future, Made Human | AI innovations</title>
	<meta
		name="description"
		content="A student-friendly guide to how artificial intelligence is shaping a more thoughtful future."
	/>
</svelte:head>

<header class="site-header">
	<a class="brand" href="#top" aria-label="Future, Made Human home">
		<span class="brand-mark" aria-hidden="true"><span></span><span></span><span></span></span>
		<span>future, made <em>human</em></span>
	</a>
	<button class="menu-button" aria-expanded={menuOpen} aria-controls="site-nav" onclick={() => (menuOpen = !menuOpen)}>
		<span class="sr-only">Toggle navigation</span>
		<span class="menu-line"></span><span class="menu-line"></span>
	</button>
	<nav id="site-nav" class:open={menuOpen} aria-label="Main navigation">
		<a href="#what-is-ai" onclick={() => (menuOpen = false)}>What is AI?</a>
		<a href="#milestones" onclick={() => (menuOpen = false)}>Milestones</a>
		<a href="#innovations" onclick={() => (menuOpen = false)}>Where it helps</a>
		<a class="nav-cta" href="#responsible" onclick={() => (menuOpen = false)}>Use it wisely <span>↗</span></a>
	</nav>
</header>

<main id="top">
	<section class="hero wrapper" aria-labelledby="hero-title">
		<div class="hero-copy">
			<p class="eyebrow"><span class="eyebrow-dot"></span> A school guide to a big idea</p>
			<h1 id="hero-title">Technology with a <span>human</span> point of view.</h1>
			<p class="hero-intro">
				Artificial intelligence is changing how we learn, work, travel, and care for our planet. Let’s look
				at the innovations — and the choices — shaping our shared future.
			</p>
			<div class="hero-actions">
				<a class="button button-dark" href="#innovations">Explore the ideas <span>↓</span></a>
				<a class="text-link" href="#what-is-ai">Start with the basics <span>↗</span></a>
			</div>
		</div>
		<div class="hero-art" aria-label="Abstract illustration of connected ideas">
			<div class="art-sun"></div>
			<div class="orbit orbit-one"></div>
			<div class="orbit orbit-two"></div>
			<div class="art-node node-one">✦</div>
			<div class="art-node node-two">◌</div>
			<div class="art-node node-three">⌁</div>
			<div class="art-card">
				<span class="card-label">TODAY'S THOUGHT</span>
				<strong>Good questions<br />make better tech.</strong>
				<span class="card-arrow">↗</span>
			</div>
			<span class="art-note note-one">curiosity</span>
			<span class="art-note note-two">care</span>
		</div>
	</section>

	<section class="ticker" aria-label="Topics covered">
		<div class="ticker-track">
			<span>LEARN</span><i>✦</i><span>CREATE</span><i>✦</i><span>CONNECT</span><i>✦</i><span>CARE</span><i>✦</i>
			<span>LEARN</span><i>✦</i><span>CREATE</span><i>✦</i><span>CONNECT</span><i>✦</i><span>CARE</span>
		</div>
	</section>

	<section class="definition wrapper section-grid" id="what-is-ai" aria-labelledby="definition-title">
		<div class="section-intro">
			<p class="eyebrow">01 / The basics</p>
			<h2 id="definition-title">So, what <em>is</em> AI?</h2>
			<p class="section-lead">It’s a tool for finding patterns, making predictions, and helping people solve problems.</p>
		</div>
		<div class="definition-content">
			<div class="definition-statement">
				<div class="quote-mark">“</div>
				<p>AI is software that learns from examples to do tasks that usually need human intelligence.</p>
			</div>
			<div class="definition-points">
				<div><strong>01</strong><span><b>Learn</b> from lots of examples</span></div>
				<div><strong>02</strong><span><b>Notice</b> patterns and possibilities</span></div>
				<div><strong>03</strong><span><b>Help</b> people make informed choices</span></div>
			</div>
		</div>
	</section>

	<section class="milestones-section" id="milestones" aria-labelledby="milestones-title">
		<div class="wrapper">
			<div class="milestone-heading">
				<div>
					<p class="eyebrow">02 / A quick history</p>
					<h2 id="milestones-title">From ideas to impact.</h2>
				</div>
				<p>AI did not appear overnight. It is a story of questions, experiments, and many people building on one another’s work.</p>
			</div>
			<div class="timeline" aria-label="AI milestones timeline">
				<div class="timeline-item"><span class="timeline-year">1950</span><span class="timeline-line"></span><div><h3>A curious question</h3><p>Alan Turing asks if machines can think.</p></div></div>
				<div class="timeline-item"><span class="timeline-year">1956</span><span class="timeline-line"></span><div><h3>A field gets a name</h3><p>The term “artificial intelligence” is introduced.</p></div></div>
				<div class="timeline-item"><span class="timeline-year">1997</span><span class="timeline-line"></span><div><h3>A famous match</h3><p>IBM’s Deep Blue defeats chess champion Garry Kasparov.</p></div></div>
				<div class="timeline-item"><span class="timeline-year">Today</span><span class="timeline-line"></span><div><h3>AI in our hands</h3><p>New tools help us create, discover, and communicate.</p></div></div>
			</div>
		</div>
	</section>

	<section class="innovations wrapper" id="innovations" aria-labelledby="innovations-title">
		<div class="section-heading">
			<div><p class="eyebrow">03 / In the real world</p><h2 id="innovations-title">Ideas in action.</h2></div>
			<p>Look around and you’ll find AI helping with challenges both big and small.</p>
		</div>
		<div class="filters" aria-label="Filter innovations">
			{#each areas as area}
				<button class:active={activeArea === area} onclick={() => (activeArea = area)}>{area}</button>
			{/each}
		</div>
		<div class="innovation-grid">
			{#each visibleInnovations as innovation}
				<article class="innovation-card">
					<div class={`innovation-icon ${innovation.color}`}>{innovation.icon}</div>
					<div class="innovation-meta"><span>{innovation.kicker}</span><span>0{innovations.indexOf(innovation) + 1}</span></div>
					<h3>{innovation.title}</h3>
					<p>{innovation.description}</p>
					<a href="#responsible" aria-label={`Learn about responsible ${innovation.title} innovation`}>Read the note <span>↗</span></a>
				</article>
			{/each}
		</div>
	</section>

	<section class="responsible wrapper" id="responsible" aria-labelledby="responsible-title">
		<div class="responsible-art" aria-hidden="true"><div class="big-sun"></div><div class="spark spark-a">✦</div><div class="spark spark-b">✦</div><div class="spark spark-c">✦</div></div>
		<div class="responsible-copy">
			<p class="eyebrow">04 / The human part</p>
			<h2 id="responsible-title">Powerful tools need thoughtful people.</h2>
			<p>AI can be useful, but it is not magic — and it is never neutral. The data and instructions people choose shape what it does.</p>
			<div class="principles">
				<div><span>01</span><h3>Ask who benefits</h3><p>Good design includes different experiences and voices.</p></div>
				<div><span>02</span><h3>Check the answer</h3><p>AI can be wrong, so human judgment still matters.</p></div>
				<div><span>03</span><h3>Protect people</h3><p>Privacy, safety, and fairness belong in every step.</p></div>
			</div>
		</div>
	</section>

	<section class="closing wrapper" aria-labelledby="closing-title">
		<p class="eyebrow">05 / Your turn</p>
		<h2 id="closing-title">The future is not just something we use.<br /><em>It’s something we shape.</em></h2>
		<p>Stay curious. Keep asking good questions. Build technology that leaves room for everyone.</p>
		<a class="button button-coral" href="#top">Back to the beginning <span>↑</span></a>
	</section>
</main>

<footer class="site-footer">
	<div class="wrapper footer-inner">
		<a class="brand" href="#top"><span class="brand-mark" aria-hidden="true"><span></span><span></span><span></span></span><span>future, made <em>human</em></span></a>
		<p>Made for curious minds · AI innovations, explained</p>
		<p>© 2025 School project</p>
	</div>
</footer>

<style>
	:global(*) { box-sizing: border-box; }
	:global(html) { scroll-behavior: smooth; }
	:global(body) { margin: 0; background: #fbfaf6; color: #1e2932; font-family: 'DM Sans', sans-serif; }
	:global(a) { color: inherit; text-decoration: none; }
	.wrapper { width: min(1160px, calc(100% - 64px)); margin: 0 auto; }
	.site-header { align-items: center; display: flex; justify-content: space-between; margin: 0 auto; max-width: 1320px; padding: 24px 32px; }
	.brand { align-items: center; display: inline-flex; font-size: 14px; font-weight: 700; gap: 10px; letter-spacing: -.02em; }
	.brand em { color: #ef684d; font-family: 'Playfair Display', serif; font-size: 16px; font-weight: 500; }
	.brand-mark { display: inline-flex; gap: 2px; height: 18px; transform: rotate(-12deg); width: 22px; }
	.brand-mark span { background: #ef684d; border-radius: 5px; display: block; height: 100%; transform: skew(-20deg); width: 5px; }
	.brand-mark span:nth-child(2) { background: #f5ad52; height: 75%; margin-top: 4px; }
	.brand-mark span:nth-child(3) { background: #83b8a4; height: 55%; margin-top: 8px; }
	nav { align-items: center; display: flex; gap: 30px; }
	nav a { color: #5e6870; font-size: 12px; font-weight: 600; }
	nav a:hover, .text-link:hover { color: #ef684d; }
	.nav-cta { border: 1px solid #d9dcd8; border-radius: 30px; color: #1e2932; padding: 11px 16px; }
	.nav-cta span { color: #ef684d; font-size: 16px; margin-left: 8px; }
	.menu-button { display: none; }
	.hero { align-items: center; display: grid; gap: 8%; grid-template-columns: 1fr 1fr; min-height: 650px; padding-bottom: 85px; padding-top: 70px; }
	.eyebrow { color: #ef684d; font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: .12em; margin: 0 0 22px; text-transform: uppercase; }
	.eyebrow-dot { background: #ef684d; border-radius: 50%; display: inline-block; height: 7px; margin-right: 8px; width: 7px; }
	h1, h2, h3, p { margin-top: 0; }
	h1, h2 { font-weight: 500; letter-spacing: -.055em; }
	h1 { font-size: clamp(48px, 6vw, 83px); line-height: .98; margin-bottom: 30px; max-width: 620px; }
	h1 span, h2 em { color: #ef684d; font-family: 'Playfair Display', serif; font-style: italic; font-weight: 500; letter-spacing: -.06em; }
	.hero-intro { color: #657078; font-size: 16px; line-height: 1.7; max-width: 440px; }
	.hero-actions { align-items: center; display: flex; gap: 26px; margin-top: 36px; }
	.button { border-radius: 28px; display: inline-flex; font-size: 12px; font-weight: 600; gap: 28px; padding: 16px 20px; }
	.button span { font-size: 18px; line-height: 10px; }
	.button-dark { background: #1e2932; color: #fff; }
	.button-dark:hover { background: #ef684d; }
	.text-link { color: #566169; font-size: 12px; font-weight: 600; }
	.text-link span { color: #ef684d; font-size: 17px; margin-left: 7px; }
	.hero-art { height: 455px; position: relative; }
	.art-sun { background: #f5ad52; border-radius: 50%; height: 270px; left: 18%; position: absolute; top: 12%; width: 270px; }
	.orbit { border: 1px solid #d4b477; border-radius: 50%; height: 360px; left: 5%; position: absolute; top: 2%; transform: rotate(34deg); width: 420px; }
	.orbit-two { border-color: #98bcae; height: 440px; left: 18%; top: -8%; transform: rotate(-46deg); width: 300px; }
	.art-node { align-items: center; border-radius: 50%; display: flex; font-size: 27px; height: 58px; justify-content: center; position: absolute; width: 58px; }
	.node-one { background: #ef684d; color: #fff; left: 8%; top: 17%; }
	.node-two { background: #fff9ed; border: 1px solid #e1c993; color: #ef684d; right: 8%; top: 9%; }
	.node-three { background: #7fb3a1; color: #fff; left: 13%; top: 77%; }
	.art-card { background: #f9f3e8; box-shadow: 0 12px 30px #a7774125; padding: 23px 26px; position: absolute; right: 3%; top: 48%; transform: rotate(-4deg); width: 185px; }
	.card-label { color: #9b835f; display: block; font-family: 'DM Mono', monospace; font-size: 8px; letter-spacing: .08em; margin-bottom: 13px; }
	.art-card strong { font-family: 'Playfair Display', serif; font-size: 22px; font-weight: 500; line-height: 1.1; }
	.card-arrow { color: #ef684d; display: block; font-size: 24px; margin-top: 12px; }
	.art-note { color: #79857e; font-family: 'Playfair Display', serif; font-size: 15px; font-style: italic; position: absolute; }
	.note-one { right: 1%; top: 28%; transform: rotate(11deg); }.note-two { left: 0; top: 63%; transform: rotate(-12deg); }
	.ticker { background: #1e2932; color: #f8f5ec; overflow: hidden; padding: 18px 0; }
	.ticker-track { align-items: center; display: flex; font-family: 'DM Mono', monospace; font-size: 11px; gap: 42px; justify-content: center; letter-spacing: .2em; white-space: nowrap; }
	.ticker-track i { color: #ef684d; font-size: 14px; font-style: normal; }
	.section-grid { display: grid; gap: 12%; grid-template-columns: .8fr 1.2fr; padding-bottom: 140px; padding-top: 145px; }
	h2 { font-size: clamp(40px, 5vw, 64px); line-height: 1; margin-bottom: 28px; }
	.section-lead, .section-heading > p { color: #657078; font-size: 15px; line-height: 1.7; max-width: 275px; }
	.definition-statement { border-bottom: 1px solid #d9ded9; border-top: 1px solid #d9ded9; display: flex; gap: 20px; padding: 28px 0; }
	.quote-mark { color: #ef684d; font-family: 'Playfair Display', serif; font-size: 56px; line-height: .7; }
	.definition-statement p { font-family: 'Playfair Display', serif; font-size: 28px; line-height: 1.2; margin: 0; max-width: 550px; }
	.definition-points { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; padding-top: 30px; }
	.definition-points div { align-items: flex-start; display: flex; flex-direction: column; gap: 14px; }
	.definition-points strong, .principles span { color: #ef684d; font-family: 'DM Mono', monospace; font-size: 10px; }
	.definition-points span { color: #68737a; font-size: 12px; line-height: 1.4; }.definition-points b { color: #1e2932; display: block; }
	.milestones-section { background: #e6f0e9; padding: 100px 0 115px; }
	.milestone-heading, .section-heading { align-items: end; display: flex; justify-content: space-between; }
	.milestone-heading > p { color: #64766e; font-size: 14px; line-height: 1.6; margin: 0 0 9px; max-width: 300px; }
	.milestone-heading h2, .section-heading h2 { margin-bottom: 0; }
	.timeline { display: grid; gap: 0; grid-template-columns: repeat(4, 1fr); margin-top: 80px; }
	.timeline-item { min-height: 190px; position: relative; }
	.timeline-year { color: #ef684d; font-family: 'DM Mono', monospace; font-size: 11px; }
	.timeline-line { background: #95b3a5; display: block; height: 1px; margin: 20px 0 23px; position: relative; width: 100%; }
	.timeline-line:before { background: #ef684d; border: 3px solid #e6f0e9; border-radius: 50%; content: ''; height: 8px; left: -1px; position: absolute; top: -7px; width: 8px; }
	.timeline-item h3 { font-size: 16px; margin-bottom: 11px; }.timeline-item p { color: #64766e; font-size: 12px; line-height: 1.5; max-width: 180px; }
	.innovations { padding-bottom: 145px; padding-top: 140px; }.section-heading > p { margin-bottom: 8px; }
	.filters { display: flex; gap: 8px; margin: 55px 0 22px; }.filters button { background: transparent; border: 1px solid #d8ddd9; border-radius: 20px; color: #707a7f; cursor: pointer; font: 11px 'DM Sans', sans-serif; padding: 9px 16px; }.filters button:hover, .filters button.active { background: #1e2932; border-color: #1e2932; color: #fff; }
	.innovation-grid { display: grid; gap: 12px; grid-template-columns: repeat(5, 1fr); }.innovation-card { border: 1px solid #e0e3df; display: flex; flex-direction: column; min-height: 325px; padding: 20px; transition: transform .2s, box-shadow .2s; }.innovation-card:hover { box-shadow: 0 14px 28px #2c3b3210; transform: translateY(-5px); }.innovation-icon { align-items: center; border-radius: 50%; display: flex; font-size: 27px; height: 62px; justify-content: center; margin-bottom: 30px; width: 62px; }.coral { background: #f7c2b6; color: #c74f3c; }.sun { background: #f9dfad; color: #bb7c27; }.mint { background: #c8dfd3; color: #4a9075; }.blue { background: #c6dce4; color: #4e8195; }.lilac { background: #dbd2e5; color: #7f6198; }
	.innovation-meta { color: #8a9493; display: flex; font: 9px 'DM Mono', monospace; justify-content: space-between; letter-spacing: .08em; text-transform: uppercase; }.innovation-card h3 { font-size: 19px; margin: 9px 0; }.innovation-card p { color: #70797c; font-size: 12px; line-height: 1.55; }.innovation-card a { color: #ef684d; font-size: 11px; font-weight: 600; margin-top: auto; }.innovation-card a span { font-size: 16px; margin-left: 6px; }
	.responsible { align-items: center; background: #f6e9d8; display: grid; gap: 10%; grid-template-columns: .8fr 1.2fr; margin-bottom: 140px; min-height: 570px; padding: 65px 8%; }.responsible-art { height: 350px; position: relative; }.big-sun { background: #edc58f; border-radius: 50%; height: 275px; left: 11%; position: absolute; top: 11%; width: 275px; }.spark { color: #ef684d; font-size: 26px; position: absolute; }.spark-a { left: 4%; top: 24%; }.spark-b { right: 4%; top: 12%; }.spark-c { bottom: 17%; right: 17%; }.responsible-copy h2 { max-width: 450px; }.responsible-copy > p:not(.eyebrow) { color: #756e66; font-size: 14px; line-height: 1.65; max-width: 435px; }.principles { display: grid; gap: 18px; grid-template-columns: repeat(3, 1fr); margin-top: 35px; }.principles h3 { font-size: 13px; margin: 10px 0 8px; }.principles p { color: #827b73; font-size: 11px; line-height: 1.5; }
	.closing { padding: 0 0 150px; text-align: center; }.closing h2 { margin: 0 auto 20px; max-width: 770px; }.closing > p:not(.eyebrow) { color: #7a8488; font-size: 14px; margin: 0 auto 32px; }.button-coral { background: #ef684d; color: #fff; }.button-coral:hover { background: #d9533b; }
	.site-footer { background: #1e2932; color: #fff; padding: 27px 0; }.footer-inner { align-items: center; display: flex; justify-content: space-between; }.footer-inner p { color: #9aa6aa; font-size: 10px; margin: 0; }.footer-inner .brand { color: #fff; }
	.sr-only { height: 1px; margin: -1px; overflow: hidden; position: absolute; width: 1px; clip: rect(0,0,0,0); }
	@media (max-width: 850px) { .wrapper { width: min(100% - 40px, 600px); }.site-header { padding: 20px; }.menu-button { background: transparent; border: 0; display: block; padding: 8px; }.menu-line { background: #1e2932; display: block; height: 2px; margin: 5px 0; width: 22px; } nav { background: #fbfaf6; box-shadow: 0 14px 25px #1e29321a; display: none; flex-direction: column; gap: 22px; left: 0; padding: 28px 20px; position: absolute; right: 0; top: 67px; z-index: 5; } nav.open { display: flex; } .hero { display: block; min-height: 0; padding-bottom: 65px; padding-top: 55px; }.hero-art { margin: 50px auto 0; max-width: 480px; }.section-grid, .responsible { display: block; }.section-intro { margin-bottom: 55px; }.timeline { grid-template-columns: repeat(2, 1fr); row-gap: 35px; }.innovation-grid { grid-template-columns: repeat(2, 1fr); }.innovation-card:last-child { grid-column: span 2; }.responsible { margin-bottom: 90px; padding: 50px 28px; }.responsible-art { margin-bottom: 30px; }.footer-inner { align-items: flex-start; flex-direction: column; gap: 16px; } }
	@media (max-width: 500px) { h1 { font-size: 49px; }.hero-art { height: 340px; transform: scale(.82); transform-origin: top left; width: 122%; }.section-grid { padding-bottom: 90px; padding-top: 90px; }.definition-points { gap: 12px; }.definition-statement p { font-size: 23px; }.milestones-section { padding: 80px 0; }.milestone-heading, .section-heading { align-items: flex-start; display: block; }.milestone-heading > p, .section-heading > p { margin-top: 22px; }.timeline { margin-top: 55px; }.innovation-grid { grid-template-columns: 1fr; }.innovation-card:last-child { grid-column: auto; }.innovations { padding-bottom: 95px; padding-top: 90px; }.filters { flex-wrap: wrap; margin-top: 35px; }.principles { grid-template-columns: 1fr; }.responsible-art { height: 250px; }.big-sun { height: 210px; width: 210px; }.closing { padding-bottom: 100px; }.closing h2 br { display: none; } }
</style>
