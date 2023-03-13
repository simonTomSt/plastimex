<script>
	import logo from '$lib/images/homePage/logo.png';
	import { t } from '$lib/translations';
</script>

<header>
	<nav class="navbar navbar-expand-lg navbar-light bg-light">
		<span class="navbar-brand">
			<img src={logo} alt={t.homePage.logo.alt} />
		</span>

		<div class="collapse navbar-collapse" id="navbarSupportedContent">
			<ul class="navbar-nav m-auto">
				<li class="nav-item first">
					<a class="nav-link" href="/transport">Plastimex-Transport</a>
				</li>

				<li class="nav-item second">
					<a class="nav-link" href="/nawozy">Plastimex-Nawozy</a>
				</li>
			</ul>
		</div>
	</nav>
</header>

<style>
	.navbar {
		background-color: rgb(5, 157, 204) !important;
	}

	.navbar-brand {
		position: absolute;
		left: 50%;
		top: 0;
		transform: translate(-50%, -50%);
		background-color: rgb(255, 255, 255);
		width: 450px;
		height: 450px;
		border-radius: 360px;
		z-index: 3;
		border: 2px black solid;
	}

	.navbar:hover img {
		filter: brightness(130%);
	}

	.navbar img {
		width: 270px;
		position: absolute;
		left: 50%;
		bottom: 5%;
		transform: translateX(-50%);
		transition: 0.3s;
	}

	.nav-item a {
		color: #fff !important;
	}

	.nav-item.first {
		position: relative;
		top: 0;
		right: 290px;
	}

	.nav-item.second {
		position: relative;
		top: 0;
		left: 270px;
	}

	@media only screen and (max-width: 994px) {
		.navbar-brand {
			position: absolute;
			left: 0%;
			top: 0;
			transform: translate(10%, -50%);
			background-color: rgb(255, 255, 255);
			width: 170px;
			height: 170px;
			border-radius: 360px;
		}
		.navbar img {
			width: 100px;
			left: 49%;
			bottom: 5%;
		}
	}
</style>
