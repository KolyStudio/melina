<script>
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import dayjs from 'dayjs';

	const date = dayjs().format('DD/MM/YYYY');
	let monip = '';
	let online = 'EN LIGNE';
	let show = false;
	let show2 = false;
	let show3 = false;
	let myTxt = '';

	const { id } = $page.params;
	const prenom = id.slice(0).charAt(0).toUpperCase() + id.slice(1);
	const name = id.toUpperCase();
	const proof = id.toLowerCase();

	let titre = `${prenom} - Page Privée`;

	onMount(async () => {
		var myArray = [
			`EN LIGNE À L'INSTANT`,
			'EN LIGNE IL Y A 3 MINUTES',
			'EN LIGNE IL Y A 4 MINUTES'
		];
		online = myArray[Math.floor(Math.random() * myArray.length)];

		const resulta = await fetch('https://ipinfo.io/?token=cb83f69067b70b').then((r) => r.json());

		const ipay = await fetch(
			`https://api.ipregistry.co/` + resulta.ip + `?key=6nn8zr4k2hcwkw32`
		).then((r) => r.json());

		console.log(ipay.carrier.name);

		if (!ipay.carrier.name) {
			monip = `vers ` + ipay.location.city;
		} else {
			monip = '';
		}
	});

	function showDeux() {
		show = true;
	}
</script>

<svelte:head>
	<title>{titre}</title>
	<script async defer src="https://tools.luckyorange.com/core/lo.js?site-id=5e7fce81"></script>

	<script async src="https://c.opfourpro.com/8/js/script.js?id=wOa6H"></script>
	<meta
		name="description"
		content={`Accéder à la page privée de ${prenom} pour consulter sa présentation et ses photos. ${prenom} répond généralement aux messages privés en moins d'une heure.`}
	/>
	<meta
		name="og:description"
		content={`Accéder à la page privée de ${prenom} pour consulter sa présentation et ses photos. ${prenom} répond généralement aux messages privés en moins d'une heure.`}
	/>
	<meta
		name="twitter:description"
		content={`Accéder à la page privée de ${prenom} pour consulter sa présentation et ses photos. ${prenom} répond généralement aux messages privés en moins d'une heure.`}
	/>
	<link rel="icon" href="favicon.png" />
</svelte:head>

<h1 class="hidden">{prenom}</h1>
<div class="hidden">
	Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond
	généralement aux messages privés en moins d'une heure.
</div>
<div class="relative lg:w-5/12 lg:m-auto">
	<div class="flex  mt-2 relative w-full justify-center rounded-full">
		<div class="flex justify-center absolute right-0 left-0 top-[10px]">
			<div
				class="text-white fade-inn rounded-lg  bg-[#09BC8A]  px-3 py-1 text-center text-xs font-semibold uppercase"
			>
				EN LIGNE
			</div>
		</div>

	</div>

	<div class="mt-4 flex space-x-2  pt-2 uppercase text-[#d6dce8] justify-center">
		<div class="  font-semibold rounded-[5px] px-2 text-sm">🎂 20 ans</div>
		<div class=" font-semibold rounded-[5px] px-2 text-sm">📍 À 9 km</div>
		<div class="font-semibold rounded-[5px] px-2 text-sm">🍑 Libertine</div>
	</div>

	<div class="text-[#e6e6fa]  w-[90%] m-auto my-4 text-center">
		<p class="py-2 font-medium ">
			À la recherche d'un plan cul vers {monip} pour m'amuser un peu ! 😘
			<br />
			<br />Si tu es intéressé, inscris toi ici et envoie moi un message
			<br />
			👇👇👇
		</p>
	</div>

	<div
		on:click={showDeux}
		class="cursor-pointer shake bg-gradient-to-r  from-[#ef476f] to-[#ef476f] border-b-4 border-[#c43b5b] text-white text-lg font-medium py-4 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
	>
		<div>{` ME CONTACTER MAINTENANT `}</div>
	</div>



	<div class="w-[95%] m-auto p-3 rounded-3xl my-4">
		<h2 class="font-semibold text-[#ef476f]">JE NE SUIS PAS UNE ESCORTE !! ❌</h2>
		<p class="py-2 text-[#e6e6fa] text-sm">
			Une bonne fois pour toutes, je ne demande <b>pas d'argent,</b> je cherche juste des plans culs
			pour m'amuser un peu, c'est tout.
			<br />
			<br />
			Je préfère généralement les mecs avec <b> un peu d'expérience </b>{' '}
			mais si tu es puceau, je vais voir ce que je peux faire... 😉
			<br />
			<br /> Par contre les mecs,{' '}
			<b>respect et discrétion obligatoire SVP,</b> sinon je bloque car c'est pas ce que je recherche.
		</p>
	</div>

	<div class="w-[95%] m-auto p-3 rounded-3xl my-4 mt-2 ">
		<h2 class="font-semibold text-[#ef476f]">COMMENT ME RENCONTRER EN RÉEL ?</h2>
		<p class="py-2 text-[#e6e6fa] text-sm">
			Envoie-moi une petite photo sur{' '}
			<span class="cursor-pointer text-blue-600 font-medium underline underline-offset-2">
				<span on:click={showDeux}> MyClub en cliquant ici </span>
			</span>{' '}
			et <b>dis-moi quand t'es dispo.</b> Je reçois les notifs quand j'ai un message, donc
			habituellement,
			<b> je répond en quelques minutes.</b>
			<br />
			<br />
			Je préviens l'essai coûte quelque chose comme 1 ou 2 euros mais ensuite t'es tranquille tu peux
			contacter
			<b> autant de filles que tu veux.</b>
			<br />
			<br />
			Et au moins, je ne me fais pas harceler comme sur Tinder, Badoo ou Snap,
			<b> ça me permet de te parler sans me faire spammer</b> par des miliers des gros relous. 😘
		</p>
	</div>

	<div
		on:click={showDeux}
		class="cursor-pointer shake bg-gradient-to-r  from-[#ef476f] to-[#ef476f] border-b-4 border-[#c43b5b] text-white text-lg font-medium py-4 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
	>
		<div>{` CLIQUE ICI POUR VOIR MON PROFIL `}</div>
	</div>

	<div class="w-[95%] m-auto p-3 rounded-3xl mt-6">
		<h2 class="font-semibold text-center text-[#ef476f]">QUELQUES TÉMOIGNAGES</h2>
	</div>

	<div class="py-3">
		<div class="w-[85%] bg-white m-auto p-3 rounded-3xl my-2 ">
			<img alt={prenom} src="reviews/rev1.webp" />
		</div>
		<div class="text-center m-auto w-[85%] font-medium text-white text-sm">
			Vous êtes nombreux à avoir pris l'offre d'essai et à en être contents apparements ! 😘
		</div>
	</div>

	<div class="py-3">
		<div class="w-[85%] bg-white m-auto p-3 rounded-3xl my-2 ">
			<img alt={prenom} src="reviews/rev2.webp" />
		</div>

		<div class="text-center m-auto w-[85%] font-medium text-white text-sm">
			Pour ceux qui sont sceptiques, testez au moins avec l'offre d'essai, vous verrez que ça
			fonctionne vraiment ! 💯🔥
		</div>
	</div>

	<div class="py-3">
		<div class="w-[85%] bg-white m-auto p-3 rounded-3xl my-2">
			<img alt={prenom} src="reviews/rev3.webp" />
		</div>
		<div class="text-center m-auto w-[85%] font-medium text-white text-sm">
			Ce ne sont pas des escortes, vous pouvez contacter autant de filles que vous voulez. 👌
		</div>
	</div>

	<footer class="">
		<div class="w-[90%] m-auto text-center text-white text-sm">
			<div class="text-[#ef476f] text-center text-xl font-medium my-2">
				Tu veux nous rejoindre ?
			</div>
			<div>
				Super, tu ne le regretteras pas ! 🔥<br />
				<br />
				Et si tu doutes encore tu peux tester quelques jours avec l'offre d'essai ! <br />
				<br />Il te suffit de cliquer sur le bouton ci-dessous, de t'inscrire en une minute puis de
				choisir une offre !<br />
				<br />👇👇👇
			</div>
		</div>

		<div
			on:click={showDeux}
			class="cursor-pointer shake bg-gradient-to-r  from-[#ef476f] to-[#ef476f] border-b-4 border-[#c43b5b] text-white text-lg font-medium py-4 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
		>
			<div>{` S'INSCRIRE SUR MYCLUB `}</div>
		</div>
	</footer>

	<div class={show ? 'show' : 'noshow'}>
		<div class="backdrop-brightness-[.15] fixed top-0 h-full w-full text-white lg:w-5/12">
			<div class="relative flex justify-center items-center h-screen w-full ">
				<div class=" bg-[#1b1c21] w-[95%] m-auto h-[auto] rounded-xl relative">
					<div class="flex  space-x-2 px-1 justify-center mt-2 items-center">
						<div class="flex justify-center items-center my-2 relative w-[200px] m-auto">
							<img src="/profil.webp" alt={prenom} class="rounded-[50px]  w-[170px]" />
							<div
								class="h-6 w-6 rounded-full border-[4px] border-[#1b1c21] bg-[#09BC8A] absolute bottom-0 right-0"
							/>
						</div>
						<div class="text-[white] font-medium">
							Afin de ne parler qu'à des majeurs, {prenom} ne souhaite parler qu'aux hommes inscrits.{' '}
						</div> 
					</div>
					<div id="form" />
				</div>
			</div>
		</div>
	</div>
</div>
