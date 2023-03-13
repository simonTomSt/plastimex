<script>
	import { t } from '$lib/translations';
	import Footer from '$lib/components/Footer.svelte';
	import Header from './components/Header.svelte';
	import fertilizersPhoto from '$lib/images/homePage/fertilizers.jpg';
	import transportPhoto from '$lib/images/homePage/transport.jpg';
</script>

<svelte:head>
	<title>{t.homePage.meta.title}</title>
	<meta name="description" content={t.homePage.meta.desc} />
</svelte:head>

<div class="body">
	<main>
		<Header />

		<section class="welcome">
			<div class="row">
				<div class="tile first-tile col-lg">
					<a href="https://www.plastimex-dziadak.pl/transport-gabarytowy-miedzynarodowy-krajowy">
						<img
							src={transportPhoto}
							alt="transport ponadgabarytowy, usługi spedycyjne, transport działoszyn"
						/>
						<h2 class="option">Transport</h2>
					</a>
				</div>

				<div class="tile second-tile col-lg">
					<a href="https://www.plastimex-dziadak.pl/granulowane-wapno-nawozowe">
						<img
							src={fertilizersPhoto}
							alt="nawozy, sprzedaż wapna nawozowego, wapno granulowane działoszyn"
						/>
						<h2 class="option">Nawozy</h2>
					</a>
				</div>
			</div>
		</section>

		<Footer />
	</main>
</div>

<style>
	.body {
		background-color: rgb(1, 7, 29);
		max-height: 100vh;
		min-height: 100vh;
		overflow: hidden;
	}

	.tile {
		width: 50%;
		height: calc(100vh - 120px);
		overflow: hidden;
		position: relative;
	}

	.tile img {
		transition: 0.4s;
		filter: brightness(60%);
		min-width: 110%;
		min-height: 100%;
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
	}

	.first-tile img {
		left: 60%;
		top: 50%;
	}

	.tile:hover img {
		filter: brightness(90%);
		transform: translate(-50%, -50%) scale(1.01);
		cursor: pointer;
	}

	.tile:hover a > .option::after,
	.tile:hover a > .option::before {
		width: 100%;
	}

	.option::before {
		content: '';
		height: 7px;
		width: 40%;
		background-color: rgb(0, 195, 255);
		position: absolute;
		top: 0;
		left: 50%;
		transform: translateX(-50%);
		transition: 0.4s;
		border-radius: 5px;
	}

	.option {
		font-size: 5rem;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-75%, -50%);
		color: rgb(255, 255, 255);
		padding: 15px;
		cursor: pointer;
		transition: 0.4s;
	}

	.option::after {
		content: '';
		height: 7px;
		width: 40%;
		background-color: rgb(0, 195, 255);
		position: absolute;
		bottom: -10%;
		left: 50%;
		transform: translateX(-50%);
		transition: 0.4s;
		border-radius: 5px;
	}

	.option:hover::after,
	.option:hover::before {
		width: 100%;
	}

	.second-tile > a .option {
		transform: translate(-25%, -50%);
	}

	.first-tile {
		-webkit-clip-path: polygon(25% 0%, 100% 0%, 100% 100%, 0% 100%);
		clip-path: polygon(0 0, 100% 0%, 75% 100%, 0% 100%);
		margin-right: -7vw;
		background-image: url('../img/transport.jpg');
		background-position: center;
		background-size: cover;
	}

	.second-tile {
		-webkit-clip-path: polygon(25% 0%, 100% 0%, 100% 100%, 0% 100%);
		clip-path: polygon(25% 0%, 100% 0%, 100% 100%, 0% 100%);
		margin-left: -7vw;
		background-position: center;
		background-size: cover;
	}

	@media only screen and (max-width: 994px) {
		.tile {
			width: 100%;
			height: calc(50vh - 40px);
		}
		.option {
			font-size: 3.5rem;
			transform: translate(-50%, -50%);
		}
		.first-tile {
			clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
			margin-right: 0vw;
		}
		.second-tile {
			clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
			margin-left: 0vw;
		}
		.second-tile > a .option {
			transform: translate(-50%, -50%);
		}
	}
</style>
