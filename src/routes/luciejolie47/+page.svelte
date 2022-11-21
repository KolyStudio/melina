<script>
	import axios from 'axios';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import dayjs from 'dayjs';

	const id = 'luciejolie47';

	const date = dayjs().format('DD/MM/YYYY');

	let monip = '';
	let online = 'EN LIGNE';
	let myTxt = '';
	let show = true;
	let show2 = false;
	let show3 = false;

	const prenom = id.slice(0).charAt(0).toUpperCase() + id.slice(1);
	const name = id.toUpperCase();
	const proof = id.toLowerCase(); 

	var txt = [
			'txt_01',
			'txt_02',
		];

		
	myTxt = txt[Math.floor(Math.random() * txt.length)];
		
	let link =
		`https://k.schnell-treffen.com/?abc=2ab0b5837e6c2796&xa=n&acme=wid.90880&media=social&tpls=9&v=sexy&userAge=20&userPhotos=62&userPicture=https://i.ibb.co/ZLcFYrq/favicon.png&s1=CASH&source=` + myTxt + `&s2=` +
	date +
	`&userDistance=7&userName=` +
	proof +
	``;

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

		// console.log(ipay.carrier.name)

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

	<meta  name="description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	<meta  property="og:description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	<meta  name="twitter:description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
<script async defer src="https://tools.luckyorange.com/core/lo.js?site-id=5e7fce81"></script>

</svelte:head>

<div>
	<h1 class="hidden">{prenom}</h1>
	<div class="hidden">Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure."
	</div>
	</div>

	<div class="lg:w-2/5 lg:m-auto">
	<div class={show ? 'show' : 'noshow'}>
		<div class="relative">
			<div class="flex justify-center absolute right-0 left-0 -top-2">
				<div
					class="fade-inn rounded-lg text-white bg-[#09BC8A] shadow-2xl px-3 py-1 text-center text-xs font-semibold uppercase"
				>
					{online}
				</div>  
			</div>
				
					 <video
						class="m-auto shadow-2xl rounded-[20px] w-[90%] mt-5"
						controls 
						poster="/poster.webp"
						src="/test.mp4"
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

				<div class="w-[95%] m-auto p-3 py-0 rounded-3xl  text-center mt-4">
					
				</div>

				<div class=" mt-3 relative rounded-[30px] w-[90%] m-auto p-2  text-center">
					{#if myTxt == 'txt_01'}
					<p class="py-2 font-medium">
						Je suis Julie, 22 ans, et je cherche un mec {monip} pour échanger quelques photos en privé ! 🍑 <br><br>Le plus souvent je passe par JM Date donc si ça t'intéresse, tu peux m'y rejoindre ici 😘
						<br>⬇️⬇️⬇️					
					</p>
					{:else}
					<p class="py-2 font-medium">
						Julie / 22 ans / Libertine {monip} qui s'assume 🍑 <br><br>Si tu es intéressé, envoie moi un message ici et on s'organise un truc <br>⬇️⬇️⬇️			
					</p>
				{/if}
					</div>
				<!-- <div class="flex justify-center ">
					<div class="bg-[#f5d7cf] px-2 rounded-3xl font-medium ">📍 À {monip}</div>
				</div> -->

				

				
		

		
			<a href={link}
					class="text-center  bg-gradient-to-r  from-[#800048] to-[#95195f]  border-b-4 border-[#47102f] text-white text-lg font-medium py-5 w-[90%] m-auto flex items-center justify-center rounded-3xl mb-2 space-x-4"
				>
				{#if myTxt == 'txt_01'}
					<div>ME RENCONTRER SUR JM DATE </div>
				{:else}
					<div>{`>>> ME CONTACTER MAINTENANT <<<`}</div>
				{/if}
				</a>

				<div class="h-0.5 w-[50%] m-auto bg-or mt-5"></div>

			<div class="w-[85%] bg-white m-auto rounded-3xl my-4 shadow-xl">
				<img alt="proof" src={`../proof/direct/` + proof + `.webp`} class="rounded-3xl" />
			</div>
			<div class="text-sm font-medium text-center py-1 w-[90%] m-auto ">A savoir, si je montre pas mon visage dans la vidéo c'est que je l'ai un peu retouché pour pas trop être reconnue, j'ai un boulot et une famille donc je pense que vous comprendrez pourquoi... ^^
			</div>

			<div class="h-0.5 w-[50%] m-auto bg-or mt-5"></div>

			
			<div class="w-[95%] m-auto px-3 rounded-3xl my-4">
				<h2 class="font-semibold text-or uppercase">Est-ce que c'est gratuit ? </h2>
				<p class="py-2 text-sm">
					Oui, je ne suis ni une escorte ni une prostituée, je cherche juste à m'amuser un peu sans me prendre la tête.<br> Je ne demande rien en échange, juste du respect et un minimum de discrétion. 😘

				</p>
			</div>
			
			<div class="w-[95%] m-auto px-3 rounded-3xl my-4 mt-2 ">
				<h2 class="font-semibold text-or">COMMENT ME RENCONTRER EN RÉEL ?</h2>
				<p class="py-2 text-sm">
					Si tu es intéressé, inscris-toi sur <span class="text-blue-500 font-medium underline underline-offset-2"><a href={link}>JM Date en cliquant ici</a></span> et envoie moi un message pour qu'on puisse dans un premier temps s'échanger quelques photos. <br><br>Mais pour être tout à fait honnête avec toi, je ne suis pas certaine de vouloir faire de réel donc je préfère te le dire maintenant plutôt que te faire espérer pour rien. <br><br>Par contre si c'est vraiment ce que tu cherches je sais que y'a plein d'autres filles sur JM Date qui n'attendent que ça et qui cherchent le bon mec pour se lancer. 😇

			
					
				</p>
			</div>

			{#if myTxt == 'txt_01'}
			<div class="w-[95%] m-auto p-3 rounded-3xl my-4 mt-2 ">
				<h2 class="font-semibold text-or uppercase">Pourquoi JM Date plutôt que Snap ou Tinder ?</h2>
				<p class="py-2 text-sm">
					Je suis aussi sur Tinder et plusieurs autres sites, mais au final je me fais harceler par des Kssos et les faux profils qui me font perdre beaucoup de temps... 😡 <br><br>Une pote m'a conseillée d'essayer JM Date parce que c'est ce qu'elle utilisait pour chopper régulièrement de façon discrète. Au début je ne voulais pas trop parce que des rencontres sur JM Date ça me bloquait un peu, mais au final j'adore car c'est beaucoup plus pratique et discret que Tinder. 😍 <br><br>Et ceux qui me disent "Ouais mais JM Date c'est payant, c'est abusé", vous pouvez toujours essayer Tinder et matcher avec des filles qui ont 200 matches par jour et qui ne répondent plus depuis longtemps. ^^
				</p>
			</div>
			{/if}

		

			<a href={link}
				class="text-center bg-gradient-to-r  from-[#800048] to-[#95195f]  border-b-4 border-[#47102f] text-white text-lg font-medium py-5 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
			>
			
				<div>CLIQUE ICI POUR VOIR MON PROFIL</div>
		</a>

			<div class="w-[95%] m-auto p-3 rounded-3xl mt-6">
				<h2 class="font-semibold text-center text-or">QUELQUES TÉMOIGNAGES</h2>
			</div>
		

		<div class="pb-3">
			<div class="w-[95%] bg-white m-auto p-3 rounded-3xl my-2 ">
				<img alt="review1" src="../reviews/rev1.webp" />
			</div>
			<div class="text-center m-auto w-[90%] font-medium">
				Vous êtes nombreux à avoir pris l'offre d'essai et à en être contents apparements ! 😘
			</div>
		</div>

		<div class="py-3">
			<div class="w-[95%] bg-white m-auto p-3 rounded-3xl my-2 ">
				<img alt="review1" src="../reviews/rev2.webp" />
			</div>

			<div class="text-center m-auto w-[90%] font-medium">
				Pour ceux qui sont sceptiques, testez au moins avec l'offre d'essai, vous verrez que ça
				fonctionne vraiment ! 💯🔥
			</div>
		</div>

		<div class="py-3">
			<div class="w-[95%] bg-white m-auto p-3 rounded-3xl my-2">
				<img alt="review1" src="../reviews/rev3.webp" />
			</div>
			<div class="text-center m-auto w-[90%] font-mediume">
				Ce ne sont pas des escortes, vous pouvez contacter autant de filles que vous voulez. 👌
			</div>
		</div>


		
		<div class="w-[90%] m-auto">
			<div class="text-or text-center text-xl font-medium my-2">Tu veux nous rejoindre ?</div>
			<div class="text-center text-sm font-medium">Super, tu ne le regretteras pas ! 🔥<br><br>
				Et si tu doutes encore tu peux tester quelques jours avec l'offre d'essai !<br><br> Il te suffit de cliquer sur le bouton ci-dessous, de t'inscrire en une minute puis de choisir une offre ! <br>👇👇👇</div>
			</div>
			<a href={link}
				class=" mt-2 bg-gradient-to-r  from-[#800048] to-[#95195f]  border-b-4 border-[#47102f] text-white text-lg font-medium py-5 w-[90%] m-auto flex items-center justify-center rounded-3xl my-2 space-x-4"
			>
				
				<div>{`S'INSCRIRE SUR JM DATE`}</div>
		</a>
			
		

</div>
		
	</div>

