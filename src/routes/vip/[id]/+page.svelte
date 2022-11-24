<script>
	import axios from 'axios';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import dayjs from 'dayjs';


	const { id } = $page.params;

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
	`https://www.rencontres-proximite.com/?acme=wid.90642&siteid=3461948&tpls=73&userAge=22&userPhotos=53&userPicture=https://i.ibb.co/gWP7kq4/favicon.png&s1=CASH&source=` +
	date +
	`&userDistance=7&userName=` +
	proof +
	`035`;

	onMount(async () => {
		var myArray = [
			`EN LIGNE`,
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

	<meta  name="description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	<meta  property="og:description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">
	<meta  name="twitter:description" content="Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure.">

	<!-- <meta property="og:title" content="@{prenom}">
	<meta property="profile:username" content="{prenom}">
	<meta name="twitter:title" content="@{prenom}"> -->
	<script async src="https://c.opfourpro.info/8/js/script.js?id=bAahn"></script>
	
</svelte:head>


<h1 class="hidden">{prenom}</h1>
<div class="hidden">Accéder à la page privée de {prenom} pour consulter sa présentation et ses photos. {prenom} répond généralement aux messages privés en moins d'une heure."></div>
<div class="relative">

<div class="text-white text-center font-medium py-2 bg-[#0d0d0d] fixed m-auto z-[100] w-full text-sm">OFFRE <span class="text-[#e63946] underline">ACCÈS VIP À 1.94€</span> JUSQU'À MINUIT</div>

<div class=" pt-2 h-[200px] relative bg-scroll bg-cover bg-center" style="background-image: url('../banner.webp');"> 

	<div class="flex justify-center  absolute -bottom-3 right-5">
		<div class="fade-inn rounded-lg text-white bg-[#09BC8A]  px-3 py-1 text-center text-xs font-semibold uppercase">
			{online}
		</div>
	</div>
</div>

<!-- <div class="flex justify-center flex-col items-center pt-10">
	<img src="/logo.png" class="w-[150px] mt-4" alt={prenom}/>
</div> -->

<div class="flex  -mt-20 relative w-[125px]  ml-5 border-[5px] border-[#09BC8A] rounded-full">
	<img src="/profil.webp" alt={prenom} class="rounded-full border-[4px] border-white w-[120px] h-[120px] shadow-2xl" />
	<!-- <div class="h-6 w-6 rounded-full border-[4px] border-[white] bg-[#09BC8A] absolute bottom-0 right-12"></div> -->
</div>



<div class="flex space-x-2 items-center justify-between  mx-8 mt-2">
	<div class="flex  items-center space-x-2">
	<h3 class="uppercase text-white font-semibold text-xl text-center">{prenom}035</h3>
	<img alt={prenom} src="/icons/verified.webp" class=" w-5 h-5"/>
	</div>
	
</div>




<div class="flex space-x-2 ml-8 pt-2">
	<div class="bg-[#232323] text-white font-semibold rounded-[5px] px-2 text-sm">🎂 22 ans</div>
	<div class="bg-[#232323] text-white font-semibold rounded-[5px] px-2 text-sm">📍 À 8 km</div>
	<div class="bg-[#232323] text-white font-semibold rounded-[5px] px-2 text-sm">🍑 Libertine</div>
</div>




<!-- <div class="flex justify-center space-x-5 my-4">
	<div class="bg-white font-semibold rounded-lg px-2">🎂 20 ans</div>
	<div class="bg-white font-semibold rounded-lg px-2">📍 À 9 km</div>
</div> -->



<div class=" my-4 relative rounded-[25px] w-[98%] m-auto px-4">
	<div class="text-gray-300 font-medium uppercase pb-2">À Propos</div>
	<p class=" text-white ">
		À la recherche d'un plan cul <b>{monip}</b> pour m'amuser un peu  🍑 <br><br>Si tu veux reçevoir <b>mes nudes et me rencontrer,</b> inscris-toi ici et envoie moi un message
		<br>
	</p>
</div>

<!-- <div class="h-0.5 w-[50%] m-auto bg-gray-100 mt-2"></div> -->




	<div class="m-auto w-[90%] text-white font-medium py-2 text-center">
		J'ai un petit message pour toi.. 🔉
		<audio class="w-full pt-2"
			controls
			src="/vocal.m4a">
		</audio>
	</div>

	<div class="flex space-x-2 mt-4 justify-center"><img alt={prenom} src="/icons/arrow.png" class="w-4 rotate-90"/>
		<img alt={prenom} src="/icons/arrow.png" class="w-4 rotate-90"/>
		<img alt={prenom} src="/icons/arrow.png" class="w-4 rotate-90"/></div>
	
	

<div on:click={showDeux} class=" mt-4 bg-gradient-to-r tracking-widest  bg-[#e63946] border-b-4 border-[#ba2f3a] text-white text-lg font-medium py-4 w-[90%] m-auto flex items-center justify-center rounded-[25px] shadow-xl my-2 space-x-4">
	<!-- <img alt={prenom} src="/icons/lock.png" class="w-8"/> -->
	<div>REJOINDRE MON VIP - 1,94€</div>
</div>





<div class="flex justify-center my-6 relative w-[90%] m-auto">
	<img src="/proof/julie.webp" alt={prenom} class="rounded-[50px]   shadow-2xl" />
</div>

<div class="h-0.5 w-[50%] m-auto bg-gray-100 mt-5"></div>

<div class="text-white relative rounded-[25px] w-[98%] m-auto p-4">
	<h4 class="uppercase font-semibold pb-2">JE NE SUIS PAS UNE ESCORTE !! ❌</h4>
	
	<p>Je recherche des mecs discrets et sérieux pour m’amuser en réel ou virtuel <b>(j’adore envoyer des nudes)</b> ou pour faire <b>des soirées libertines.</b>

<br><br>
Je ne demande pas d’argent mais le site sur lequel je suis demande un paiement de <b>1.94€ pour vérifier que tu es bien majeur,</b> ça te permet d’avoir accès à tout mon contenu VIP sans avoir à payer plus.		<br><br>
		Mais si tu es là pour moi ça ne devrait pas te poser problème de toute façon… 😘</p>
</div>

<div class="h-0.5 w-[50%] m-auto bg-gray-100 mt-5"></div>

<div class="flex justify-center my-6 relative w-[90%] m-auto">
	<img src="/p2.webp" alt={prenom} class="rounded-[50px]   shadow-2xl" />
</div>


<div class=" bg-white  relative rounded-[25px] w-[90%] m-auto ">
	<div class="relative">
	<div class="shadow-2xl px-4 m-auto  space-x-4 flex items-center uppercase text-center font-bold mb-4 bg-gradient-to-r z-[100] from-[#e63946] to-[#f1616d] text-white py-5 rounded-t-[25px] text-lg">
		<img src="/icons/diamond.svg" class="w-12 -rotate-[15deg]" alt={prenom} />
		
		<div class="text-left">
			<h3>GROUPE VIP DE {prenom}035</h3>
			<h4 class="font-medium text-sm text-gray-200">Les avantages du VIP</h4> </div>
		</div>
	<!-- <div class="h-5 w-5 bg-[#e63946] m-auto rotate-45 -mt-7 z-[-1]"></div> -->
</div>
	

	<div class="h-0.5 w-[50%] m-auto bg-gray-100 mt-5"></div>
	
	<div class="font-medium text-sm flex flex-col space-y-4 p-4">
	<div>🔞 ┇ Accès à toutes mes nudes & vidéos perso</div>
	<div>🍆 ┇ Je peux noter ta b*te en privé (j’adore ça)</div>
	<div>🔥 ┇ Possibilité de se rencontrer (si feeling)</div>
	<div>📷 ┇ Cam vidéo ensemble (30min)</div>
	<div>💬 ┇ Chat en illimité avec moi mes copines</div>
	<div>🌟 ┇ Accès à mes soirées libertines privées</div>

	<div class="h-0.5 w-[50%] m-auto bg-gray-100 mt-5"></div>
</div>
	<div class="flex justify-center font-medium space-x-4 items-center">
		<div class="text-center text-[#ff4040] text-4xl line-through">60€</div>
		<div class="text-center text-[#59c86a] text-3xl">1.94€</div>
	</div>

	<div class="font-medium text-center py-2">🚨 Plus que <span class="text-[#e63946] underline font-semibold">2 places</span> restantes</div>

</div>

<!-- <div class=" bg-white my-6 relative rounded-[25px] w-[90%] m-auto p-6">
	<h4 class="uppercase text-center font-semibold pb-2">COMMENT ME RENCONTRER ? 🍑</h4>
	<p>Envoie-moi une photo sur J&M Date et <b>dis-moi quand t'es dispo.</b> Je reçois les notifs quand j'ai un message donc habituellement <b>je réponds en quelques minutes.</b><br><br>
	Je préviens l'inscription (essai) coûte quelque chose comme 1 ou 2 euros mais ensuite t'es tranquille, tu peux contacter gratuitement <b>autant de filles que tu veux.</b><br><br>
    Et au moins je ne me fais pas harceler comme sur <b>Tinder ou Snap ça permet de parler sans se faire spammer</b>, par des milliers de gros relous. 😘
	</p>
</div> -->




<div class="flex space-x-2 mt-4 justify-center"><img alt={prenom} src="/icons/arrow.png" class="w-4 rotate-90"/>
	<img alt={prenom} src="/icons/arrow.png" class="w-4 rotate-90"/>
	<img alt={prenom} src="/icons/arrow.png" class="w-4 rotate-90"/></div>



<div on:click={showDeux} class=" mt-4 bg-gradient-to-r tracking-widest  bg-[#e63946] border-b-4 border-[#ba2f3a] text-white text-lg font-medium py-4 w-[90%] m-auto flex items-center justify-center rounded-[25px] shadow-xl my-2 space-x-4">
<!-- <img alt={prenom} src="/icons/lock.png" class="w-8"/> -->
<div>REJOINDRE MON VIP - 1,94€</div>
</div>

<div on:click={showDeux} class="flex justify-center mt-4">
<div class="bg-[#181818] font-semibold text-white py-3 px-2 w-[50%] text-center border-b-4 border-[#e63946]">📸 169 nudes</div> 
<div class="bg-[#181818] font-semibold text-white py-3 px-2 w-[50%] text-center">📸 72 vidéos</div>
</div>

<div  on:click={showDeux} class="bg-[#232323] pt-2">

<div class="flex space-x-1 px-1">
	<div class="relative m-auto">
		<img src="/previews/c1.webp" alt={prenom} class=" shadow-2xl" />
	</div>
	<div class=" relative m-auto">
		<img src="/icons/cadenas.svg" class="absolute w-8 shadow-2xl right-[25%] left-[25%] m-auto top-[25%] bottom-[25%]" alt={prenom}/>
		<img src="/previews/p2.webp" alt={prenom} class=" shadow-2xl" />
	</div>
	<div class="relative m-auto">
		<img src="/icons/cadenas.svg" class="absolute w-8 shadow-2xl right-[25%] left-[25%] m-auto top-[25%] bottom-[25%]" alt={prenom}/>
		<img src="/previews/p3.webp" alt={prenom} class="  shadow-2xl" />
	</div>
</div>

<div class="flex space-x-1 px-1 py-1">
	<div class="relative m-auto">
		<img src="/icons/cadenas.svg" class="absolute w-8 shadow-2xl right-[25%] left-[25%] m-auto top-[25%] bottom-[25%]" alt={prenom}/>

		<img src="/previews/p4.webp" alt={prenom} class=" shadow-2xl" />
	</div>
	<div class=" relative m-auto">
		<img src="/previews/c2.webp" alt={prenom} class=" shadow-2xl" />
	</div>
	<div class="relative m-auto">
		<img src="/previews/c3.webp" alt={prenom} class="  shadow-2xl" />
	</div>
</div>

<div class="flex space-x-1 px-1 ">
	<div class="relative m-auto">
		<img src="/icons/cadenas.svg" class="absolute w-8 shadow-2xl right-[25%] left-[25%] m-auto top-[25%] bottom-[25%]" alt={prenom}/>
		<img src="/previews/p1.webp" alt={prenom} class=" shadow-2xl" />
	</div>
	<div class=" relative m-auto">
		<img src="/icons/cadenas.svg" class="absolute w-8 shadow-2xl right-[25%] left-[25%] m-auto top-[25%] bottom-[25%]" alt={prenom}/>
		<img src="/previews/p5.webp" alt={prenom} class=" shadow-2xl" />
	</div>
	<div class="relative m-auto">
		<img src="/icons/cadenas.svg" class="absolute w-8 shadow-2xl right-[25%] left-[25%] m-auto top-[25%] bottom-[25%]" alt={prenom}/>
		<img src="/previews/p6.webp" alt={prenom} class="  shadow-2xl" />
	</div>
</div>
</div>


<div class={show2 ? 'show2' : 'noshow2'}>
	<div
		class="fade-inn fixed w-[full] backdrop-brightness-[.30] backdrop-blur-[2px] h-full z-[10] top-0 pt-10"
	>
		<div class="fade-inn bg-[white] mt-4 w-[95%] m-auto rounded-3xl p-1">
			<div class="flex  space-x-2 px-1 justify-center mt-2 items-center">
				<div class="flex justify-center my-2 relative w-[200px] m-auto">
					<img src="/profil.webp" alt={prenom} class="rounded-[50px] border-[4px] border-white w-[170px]" />
					<div class="h-5 w-5 rounded-full border-[4px] border-white bg-[#09BC8A] absolute bottom-1 right-1"></div>
				</div>
				<div class="text-[black] font-medium">
					Tu es sur le point de rejoindre le <span class="text-[#e63946]">VIP de {prenom}035,</span> inscris-toi pour vérifier ton âge.
				</div>
			</div>
			<div id="formulaire" />
		</div>
	</div>
</div>
</div>