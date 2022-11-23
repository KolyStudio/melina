<script>
	import axios from 'axios';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import dayjs from 'dayjs';

	const id = 'marinelle061';

	const date = dayjs().format('DD/MM/YYYY');

	let monip = '';
	let online = 'EN LIGNE';
	let show = true;
	let show2 = false;
	let show3 = false;

	const prenom = id.slice(0).charAt(0).toUpperCase() + id.slice(1);
	const name = id.toUpperCase();
	const proof = id.toLowerCase(); 

	let link =
		`https://www.rencontres-proximite.com/?acme=wid.90880&siteid=3461948&tpls=73&userAge=20&userPhotos=62&userPicture=https://i.ibb.co/ZLcFYrq/favicon.png&source=JM&s1=CASH&s2=` +
		date +
		`&userDistance=8&userName=` + proof;
		


	onMount(async () => {
		var myArray = [
			`EN LIGNE À L'INSTANT`,
			'EN LIGNE IL Y A 3 MINUTES',
			'EN LIGNE IL Y A 4 MINUTES'
		];
		online = myArray[Math.floor(Math.random() * myArray.length)];

		const resulta = await fetch('https://ipinfo.io/?token=cb83f69067b70b').then((r) =>
			r.json()
		);

		const ipay = await fetch(`https://api.ipregistry.co/` + resulta.ip + `?key=6nn8zr4k2hcwkw32`).then((r) => r.json());

		console.log(ipay.carrier.name)

		if (!ipay.carrier.name) {
			monip = `vers ` + ipay.location.city;
		} else {
			monip = '';
		}
	});

	function showDeux() {
		show = false;
		show2 = true;
	}

	function showTrois() {
		show3 = true;
	}
</script>

<svelte:head>
	<title>{prenom} - Page Privée</title>

	<meta  name="description" content="Accéder à la pafge privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	<meta  property="og:description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	<meta  name="twitter:description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">


</svelte:head>

<div>
	<h1 class="hidden">{prenom}</h1>
	<div class="hidden">Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	</div>
	</div>

	<div class="lg:w-2/5 lg:m-auto">
	<div class={show ? 'show' : 'noshow'}>
		<div class="relative p-4">
			<div class="flex justify-center absolute right-0 left-0 top-[25px]">
				<div
					class="fade-inn rounded-lg text-white bg-[#09BC8A]  px-3 py-1 text-center text-xs font-semibold uppercase"
				>
					{online}
				</div>  
			</div>
				
					 <video
						class="m-auto  rounded-[20px] w-[80%] mt-5"
						controls 
						poster="/poster.webp"
						src="/proof.mp4"
						type="video/mp4"
						><track kind="captions" />
					</video>
				<!-- <img class="m-auto rounded-[20px]  border-white  border-[4px]" alt="profil" src="/poster.webp"/> -->
				
			</div>
			
			<!-- <div class="bg-[#f4f1fb] w-[95%] m-auto rounded-3xl relative mt-6">
				<div class="flex justify-center absolute right-0 left-0 -top-[10px]">
					<div
						class="fade-inn rounded-lg text-white bg-[#09BC8A]  px-3 py-1 text-center text-xs font-semibold uppercase"
					>
						{online}
					</div>
				</div> -->

					<!-- </div> -->

				<!-- <div class=" font-semibold uppercase text-2xl text-center my-2">{prenom} 🍑</div> -->

				<div class="w-[95%] m-auto p-3 py-0 rounded-3xl  text-center my-4">
					<p class="py-2 font-medium text-lg">
						À la recherche d'un plan cul {monip} pour m'amuser un peu  🍑 <br><br>Si tu es intéressé, envoie moi un message ici et on s'organise une soirée
					</p>
				</div>
				<!-- <div class="flex justify-center ">
					<div class="bg-[#f5d7cf] px-2 rounded-3xl font-medium ">📍 À {monip}</div>
				</div> -->

				

				
		

		
			<a href={link}
					class=" mt-4 bg-gradient-to-r  from-[#800048] to-[#800048]  border-b-4 border-[#540130] text-white text-lg font-medium py-5 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
				>
				
					<div>ME CONTACTER MAINTENANT</div>
				</a>

			

			<div class="w-[85%] bg-white m-auto rounded-3xl my-4 shadow-xl">
				<img alt="proof" src={`../proof/direct/` + proof + `.webp`} class="rounded-3xl" />
			</div>
			<div class="text-sm font-medium text-center py-1 w-[90%] m-auto">A savoir, si je montre pas mon visage dans la vidéo c'est que je l'ai un peu retouché pour pas trop être reconnue, j'ai un boulot et une famille donc je pense que vous comprendrez pourquoi... ^^
			</div>
			<div class="w-[95%] m-auto p-3 rounded-3xl my-4">
				<h2 class="font-semibold text-or">JE NE SUIS PAS UNE ESCORTE !! ❌</h2>
				<p class="py-2">
					Une bonne fois pour toutes, je ne demande <b>pas d'argent,</b> je cherche juste des plans
					culs pour m'amuser un peu, c'est tout.
					<br /><br />
					Je préfère généralement les mecs avec <b>un peu d'expérience</b> mais si tu es puceau, je
					vais voir ce que je peux faire... 😉
					<br /><br /> Par contre les mecs, <b>respect et discrétion obligatoire SVP,</b> sinon je bloque
					car c'est pas ce que je recherche.
				</p>
			</div>

			<div class="w-[95%] m-auto p-3 rounded-3xl my-4 mt-2 ">
				<h2 class="font-semibold text-or">COMMENT ME RENCONTRER EN RÉEL ?</h2>
				<p class="py-2">
					Envoie-moi une petite photo sur <span class="text-blue-600 font-medium underline underline-offset-2"><a href={link}>J&M Date en cliquant ici</a></span> et <b>dis-moi quand t'es dispo.</b> Je reçois
					les notifs quand j'ai un message, donc habituellement,
					<b>je répond en quelques minutes.</b>

					<br /><br />
					Je préviens l'essai coûte quelque chose comme 1 ou 2 euros mais ensuite t'es tranquille tu
					peux contacter
					<b>autant de filles que tu veux.</b>
					<br /><br />
					Et au moins, je ne me fais pas harceler comme sur Tinder, Badoo ou Snap,
					<b>ça me permet de te parler sans me faire spammer</b> par des miliers des gros relous.
				</p>
			</div>


		

			<a href={link}
				class=" bg-gradient-to-r  from-[#800048] to-[#800048]  border-b-4 border-[#540130] text-white text-lg font-medium py-5 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
			>
			
				<div>CLIQUE ICI POUR VOIR MON PROFIL</div>
		</a>

			<div class="w-[95%] m-auto p-3 rounded-3xl mt-6">
				<h2 class="font-semibold text-center text-or">QUELQUES TÉMOIGNAGES</h2>
			</div>
		

		<div class="py-3">
			<div class="w-[95%] bg-white m-auto p-3 rounded-3xl my-2 ">
				<img alt="review1" src="../reviews/rev1.webp" />
			</div>
			<div class="text-center m-auto w-[90%] font-medium ">
				Vous êtes nombreux à avoir pris l'offre d'essai et à en être contents apparements ! 😘
			</div>
		</div>

		<div class="py-3">
			<div class="w-[95%] bg-white m-auto p-3 rounded-3xl my-2 ">
				<img alt="review1" src="../reviews/rev2.webp" />
			</div>

			<div class="text-center m-auto w-[90%] font-medium ">
				Pour ceux qui sont sceptiques, testez au moins avec l'offre d'essai, vous verrez que ça
				fonctionne vraiment ! 💯🔥
			</div>
		</div>

		<div class="py-3">
			<div class="w-[95%] bg-white m-auto p-3 rounded-3xl my-2">
				<img alt="review1" src="../reviews/rev3.webp" />
			</div>
			<div class="text-center m-auto w-[90%] font-medium ">
				Ce ne sont pas des escortes, vous pouvez contacter autant de filles que vous voulez. 👌
			</div>
		</div>


		
		<div class="w-[90%] m-auto">
			<div class="text-or text-center text-xl font-medium my-2">Tu veux nous rejoindre ?</div>
			<div class="text-center">Super, tu ne le regretteras pas ! 🔥<br><br>
				Et si tu doutes encore tu peux tester quelques jours avec l'offre d'essai !<br><br> Il te suffit de cliquer sur le bouton ci-dessous, de t'inscrire en une minute puis de choisir une offre ! <br>👇👇👇</div>
			</div>
			<a href={link}
				class="shake mt-2 bg-gradient-to-r  from-[#800048] to-[#800048]  border-b-4 border-[#540130] text-white text-lg font-medium py-5 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
			>
				
				<div>{`S'INSCRIRE SUR J&M DATE`}</div>
		</a>
			
		

</div>
		
	</div>

