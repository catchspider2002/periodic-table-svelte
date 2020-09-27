<script context="module">
	export async function preload({ params }) {
	  // the `slug` parameter is available because
	  // this file is called [slug].svelte
	  const res = await this.fetch(`en/${params.slug}.json`);
	  const data = await res.json();
  
	  if (res.status === 200) {
		return { post: data };
	  } else {
		this.error(res.status, data.message);
	  }
	}
  </script>
  
  <script>
	export let post;
	import Constants from "../../components/constants.js";
	import Electron from "../../components/Electron.svelte";
	import Footer from "./_Footer.svelte";
	import Lang from "./locale.js";
	import { onMount } from "svelte";
	import { beforeUpdate, afterUpdate } from "svelte";
	let langValue = Lang.lang;
  
	let num = post.num - 1;
	let element = Constants[num];
	let previousNum, nextNum, imageSrc;
	let link2, link3, link4, link5, link6;
	let previousElement, nextElement;
  
	function id(text) {
	  return document.getElementById(text);
	}
  
	function getNum(value) {
	  if (langValue === "ar") {
		// Arabic
		value = value.toString().replace(/\./g, "٫");
		var id = ["٠", "١", "٢", "٣", "٤", "٥", "٦", "٧", "٨", "٩"];
		return value.toString().replace(/[0-9]/g, function (w) {
		  return id[+w];
		});
	  } else if (langValue === "fa") {
		// Persian
		value = value.toString().replace(/\./g, "٫");
		var id = ["۰", "۱", "۲", "۳", "۴", "۵", "۶", "۷", "۸", "۹"];
		return value.toString().replace(/[0-9]/g, function (w) {
		  return id[+w];
		});
	  } else return value;
	}
  
	function runOnLoad() {
	  id("highlight").setAttribute("transform", "translate(" + post.highlight + ")");
  
	  if (num === "1") {
		previousElement = "-";
		//   id("previousElement").innerHTML = "&mdash;";
		id("previousElement").style.textDecoration = "none";
	  } else {
		previousElement = Lang[Constants[previousNum].nme];
		id("previousElement").href = langValue + "/" + Constants[previousNum].nme;
	  }
  
	  if (num === "118") {
		nextElement = "&mdash;";
		id("nextElement").style.textDecoration = "none";
	  } else {
		nextElement = Lang[Constants[nextNum].nme];
		id("nextElement").href = langValue + "/" + Constants[nextNum].nme;
	  }
	}
  
	onMount(async () => {
	  console.log("On Mount");
	  runOnLoad();
	});
  
	beforeUpdate(() => {
	  num = post.num - 1;
	  element = Constants[num];
	  previousNum = num - 1;
	  nextNum = num - -1;
	  let link2url =
		element.num === "113" || element.num === "115" || element.num === "117" || element.num === "118" ? "element-" + element.num : element.nme;
	  let link4url = element.nme;
  
	  if (element.num === "13") link2url = link4url = "aluminum";
	  else if (element.num === "55") link2url = link4url = "cesium";
  
	  if (
		element.num === "2" ||
		element.num === "3" ||
		element.num === "5" ||
		element.num === "6" ||
		element.num === "10" ||
		element.num === "15" ||
		element.num === "18" ||
		element.num === "26" ||
		element.num === "27" ||
		element.num === "28" ||
		element.num === "36" ||
		element.num === "46" ||
		element.num === "74" ||
		element.num === "79" ||
		element.num === "80" ||
		element.num === "82" ||
		element.num === "96"
	  )
		link2url = link2url + "-chemical-element";
  
	  link2 = "https://www.britannica.com/science/" + link2url;
	  link3 = "http://www.wolframalpha.com/input/?i=" + element.nme + "+element";
	  link4 = "http://www.chemicool.com/elements/" + link4url + ".html";
	  link5 = "http://www.rsc.org/periodic-table/element/" + element.num + "/" + element.nme;
	  link6 = "http://www.webelements.com/" + element.nme + "/";
  
	  imageSrc = post.sym;
	  switch (imageSrc) {
		case "Db":
		case "Fl":
		case "Lv":
		case "Mc":
		case "Ts":
		case "Og":
		case "Nh":
		  imageSrc = "Db";
		  break;
		case "At":
		case "Tc":
		  imageSrc = "At";
		  break;
		case "Po":
		case "Ra":
		  imageSrc = "Po";
		  break;
		case "Es":
		case "Fm":
		  imageSrc = "Es";
		  break;
		case "Cn":
		case "Ds":
		case "Hs":
		case "Mt":
		case "Rg":
		  imageSrc = "Cn";
		  break;
	  }
	});
  
	afterUpdate(() => {
	  console.log("After update");
	});
  </script>
  
  <svelte:head>
	<title>{post.title}</title>
  </svelte:head>
  
  <h1>{post.title}</h1>
  
  <div class="content">
	<div class="content-wrapper">
	  <div class="container">
		<div class="masonry">
		  <div class="flex-container row">
			<div class="flex-cell">
			  <div id="firstSquare" class="flex-item masonry-col flex flex-col">
				<div id="resultNumber" class="flex line-height-normal">{element.num}</div>
				<div id="resultSymbol" class="text-center flex content-center justify-center line-height-normal">
				  <span class="self-center">{element.sym}</span>
				</div>
			  </div>
			</div>
			<div class="flex-cell">
			  <div id="secondSquare" class="flex-item masonry-col grid">
				<div class="heavyFont">{Lang.group}</div>
				<div>
				  {#if element.grp === 'na'}{Lang.na}{:else}{getNum(element.grp)}{/if}
				</div>
				<div class="heavyFont">{Lang.period}</div>
				<div>{element.prd}</div>
				<div class="heavyFont">{Lang.block}</div>
				<div>{element.blk}</div>
			  </div>
			</div>
		  </div>
		  <!-- Protons, Electrons, Neutrons -->
		  <div class="box-content masonry-col">
			<div class="grid-3">
			  <div class="new-table text-center heavyFont truncate">{Lang.protons}</div>
			  <div class="new-table text-center heavyFont truncate">{Lang.electrons}</div>
			  <div class="new-table text-center heavyFont truncate">{Lang.neutrons}</div>
			  <div class="text-center new-table font-size-1-5">{element.p}</div>
			  <div class="text-center new-table font-size-1-5">{element.e}</div>
			  <div class="text-center new-table font-size-1-5">{element.n}</div>
			</div>
		  </div>
		  <!-- General Prooperties -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.labelGeneralProp}</span>
			<div class="grid">
			  <div class="new-table heavyFont">{Lang.labelAtmNoMain}</div>
			  <div class="new-table">{element.num}</div>
			  <div class="new-table heavyFont">{Lang.labelAtmWtMain}</div>
			  <div class="new-table">{element.aWt}</div>
			  <div class="new-table heavyFont">{Lang.labelMassNum}</div>
			  <div class="new-table">{element.mNo}</div>
			  <div class="new-table heavyFont">{Lang.labelCategoryMain}</div>
			  <div class="new-table">{Lang[element.ctg]}</div>
			  <div class="new-table heavyFont">{Lang.labelColorMain}</div>
			  <div class="new-table">{Lang[element.clr]}</div>
			  <div class="new-table heavyFont">{Lang.labelRadioMain}</div>
			  <div class="new-table">{Lang[element.rdo]}</div>
			  <div class="new-table heavyFont">{Lang.labelStructureMain}</div>
			  <div class="new-table">{Lang[element.stc]}</div>
			</div>
		  </div>
		  <!-- Name Reason -->
		  <div class="box-content text-center masonry-col">
			<div class="line-height-2">
			  {@html post.reason}
			</div>
		  </div>
		  <!-- History -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.hist}</span>
			<div class="line-height-2">
			  {@html post.history}
			</div>
		  </div>
		  <!-- Electron Configuration -->
		  <div id="electronConf" class="box-content masonry-col">
			<div class="grid padding-bottom-25">
			  <div class="new-table heavyFont">{Lang.labelElectronsMain}</div>
			  <div class="new-table ltrText text-left">{element.elc}</div>
			  <div class="new-table heavyFont hyphen">{Lang.labelConfigMain}</div>
			  <div class="new-table ltrText text-left">
				{@html element.cnf}
			  </div>
			</div>
			<Electron num={element.num} sym={element.sym} />
		  </div>
		  <!-- Facts -->
		  <div class="box-content masonry-col text-center">
			<div id="elementFactsMain" class="line-height-2">
			  {@html post.facts}
			</div>
		  </div>
		  <!-- Physical Properties -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.labelPhysicalProp}</span>
			<div class="grid">
			  <div class="new-table heavyFont">{Lang.labelPhaseMain}</div>
			  <div class="new-table">{Lang[element.phs]}</div>
			  <div class="new-table heavyFont">{Lang.labelDensityMain}</div>
			  <div class="new-table">
				{#if element.dns === '-'}
				  -
				{:else}
				  {getNum(element.dns)}
				  {@html Lang.labelDensity}
				{/if}
			  </div>
			  <div class="new-table heavyFont">{Lang.labelMeltingMain}</div>
			  <div class="new-table">{element.mlt}</div>
			  <div class="new-table heavyFont">{Lang.labelBoilingMain}</div>
			  <div class="new-table">{element.bln}</div>
			  <div class="new-table heavyFont">{Lang.labelFusionMain}</div>
			  <div class="new-table">
				{#if element.fsn === 'na'}
				  {Lang.na}
				{:else}
				  {getNum(element.fsn)}
				  {@html Lang.labelFusion}
				{/if}
			  </div>
			  <div class="new-table heavyFont">{Lang.labelVaporizationMain}</div>
			  <div class="new-table">
				{#if element.vpn === 'na'}
				  {Lang.na}
				{:else}
				  {getNum(element.vpn)}
				  {@html Lang.labelFusion}
				{/if}
			  </div>
			  <div class="new-table heavyFont hyphen">{Lang.labelSpecificMain}</div>
			  <div class="new-table">
				{#if element.spc === '-'}
				  -
				{:else}
				  {getNum(element.spc)}
				  {@html Lang.labelSpecific}
				{/if}
			  </div>
			</div>
		  </div>
		  <!-- Abundance -->
		  <div class="box-content masonry-col">
			<div class="grid">
			  <div class="new-table heavyFont">{Lang.labelCrustMain}</div>
			  <div class="new-table">
				{#if element.crt === 'na'}
				  {Lang.na}
				{:else}
				  {@html getNum(element.crt)}
				{/if}
			  </div>
			  <div class="new-table heavyFont">{Lang.labelUniverseMain}</div>
			  <div class="new-table">
				{#if element.uni === 'na'}
				  {Lang.na}
				{:else}
				  {@html getNum(element.uni)}
				{/if}
			  </div>
			</div>
		  </div>
		  <!-- Image -->
		  <div class="masonry-col">
			<div class="blog-thumb">
			  <img id="elementPic" src="images/{imageSrc}.jpg" alt={post.desc} data-toggle="modal" data-target="#exampleModal" />
			</div>
			<div class="box-content bottom-rounded line-height-2">
			  <span id="imgCredits" class="heavyFont">{Lang.imgCredits}: </span>
			  <span id="imgCreditsLink" />
			  <div>
				{@html post.desc}
			  </div>
			</div>
		  </div>
		  <!-- Identifiers -->
		  <div class="box-content masonry-col">
			<div class="grid">
			  <div class="new-table heavyFont">{Lang.labelCASMain}</div>
			  <div class="new-table">{element.cas}</div>
			  <div class="new-table heavyFont">{Lang.labelCIDMain}</div>
			  <div class="new-table">
				{#if element.cid === 'na'}{Lang.na}{:else}{getNum(element.cid)}{/if}
			  </div>
			</div>
		  </div>
		  <!-- Atomic Properties -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.labelAtomicProp}</span>
			<div class="grid">
			  <div class="new-table heavyFont">{Lang.labelRadiusMain}</div>
			  <div class="new-table">
				{#if element.aRd === '-'}-{:else}{getNum(element.aRd)} pm{/if}
			  </div>
			  <div class="new-table heavyFont">{Lang.labelCovalentMain}</div>
			  <div class="new-table">
				{#if element.cRd === '-'}-{:else}{getNum(element.cRd)} pm{/if}
			  </div>
			  <div class="new-table heavyFont hyphen">{Lang.labelElectronegativityMain}</div>
			  <div class="new-table">
				{#if element.eNg === '-'}-{:else}{getNum(element.eNg)} ({Lang.pauling}){/if}
			  </div>
			  <div class="new-table heavyFont hyphen">{Lang.labelIonizationMain}</div>
			  <div class="new-table">
				{#if element.ion === '-'}-{:else}{getNum(element.ion)} {Lang.labelIonization}{/if}
			  </div>
			  <div class="new-table heavyFont">{Lang.labelVolumeMain}</div>
			  <div class="new-table">
				{#if element.vol === '-'}
				  -
				{:else}
				  {getNum(element.vol)}
				  {@html Lang.labelVolume}
				{/if}
			  </div>
			  <div class="new-table heavyFont hyphen">{Lang.labelThermalMain}</div>
			  <div class="new-table">
				{#if element.trm === '-'}-{:else}{getNum(element.trm)} {Lang.labelThermal}{/if}
			  </div>
			  <div class="new-table heavyFont hyphen">{Lang.labelOxidationMain}</div>
			  <div class="new-table ltrText text-left">{element.oxi}</div>
			</div>
		  </div>
		  <!-- Uses -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.uses}</span>
			<div class="line-height-2">
			  {@html post.uses}
			</div>
			<div />
		  </div>
		  <!-- Hazards -->
		  <div class="box-content masonry-col text-center">
			<div class="line-height-2">
			  {@html post.dangers}
			</div>
		  </div>
		  <!-- Isotopes -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.isotopes}</span>
			<div class="heavyFont padding-0 margin-y-10">{Lang.stableIsotopes}</div>
			<span class="isotopeLine">{@html post.stable}</span>
			<div class="heavyFont padding-0 margin-y-10">{Lang.unstableIsotopes}</div>
			<span class="isotopeLine">{@html post.unstable}</span>
		  </div>
		  <!-- Important Links -->
		  <div class="box-content masonry-col">
			<span class="headerOutline text-upper heavyFont">{Lang.labelLinksMain}</span>
			<div class="webLink">
			  <a id="link1" href="{Lang.wikiLink}{element.nme}" class="underlineLink" target="_blank" rel="noopener noreferrer">{Lang.wiki}</a>
			</div>
  
			<a href={link2} class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">Encyclopaedia Britannica</span></a>
			<a href={link3} class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">Wolfram Alpha</span></a>
			<a href={link4} class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">Chemicool</span></a>
			<a href={link5} class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">RSC Visual Elements</span></a>
			<a href={link6} class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">WebElements</span></a>
		  </div>
		  <!-- Small Table -->
		  <div class="box-content masonry-col">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 325 75" id="tableSVG">
			  <g transform="translate(0,-977.3622)">
				<g style="opacity: 0.4;">
				  <path transform="translate(0,977.3622)" d="m 162.5,32.5 0,20 10,0 0,20 90,0 0,-40 -90,0 -10,0 z" style="fill: #c76d6d;" />
				  <path d="m 2.5,989.86218 10,0 0,60.00002 -10,0 z" style="fill: #ba6f9c;" />
				  <path d="m 12.5,989.86218 10,0 0,60.00002 -10,0 z" style="fill: #5688aa;" />
				  <path d="m 22.5,1029.8622 150,0 0,10 -150,0 z" style="fill: #a97942;" />
				  <path d="m 22.5,1039.8622 150,0 0,10 -150,0 z" style="fill: #857d61;" />
				  <path d="m 312.5,979.8622 10,0 0,70 -10,0 z" style="fill: #529311;" />
				  <path
					transform="translate(0,977.3622)"
					d="m 262.5,22.5 0,50 10,0 10,0 10,0 10,0 0,-10 -10,0 0,-10 -10,0 0,-10 -10,0 0,-20 -10,0 z"
					style="fill: #8b77c6;" />
				  <path
					transform="translate(0,977.3622)"
					d="m 272.5,12.5 0,10 10,0 0,10 10,0 0,10 10,0 0,-30 -10,0 -10,0 -10,0 z"
					style="fill: #3f8f67;" />
				  <path d="m 302.5,989.8622 10,0 0,60 -10,0 z" style="fill: #498dad;" />
				  <path d="m 2.5,979.86218 10,0 0,10 -10,0 z" style="fill: #3f8f67;" />
				  <path
					transform="translate(0,977.3622)"
					d="m 262.5,12.5 0,10 10,0 0,-10 -10,0 z m 10,10 0,20 10,0 0,10 10,0 0,10 10,0 0,-20 -10,0 0,-10 -10,0 0,-10 -10,0 z"
					style="fill: #d1744b;" />
				  <path
					d="m 0,977.3622 0,2.5 0,70 0,2.5 325,0 0,-2.5 0,-70 0,-2.5 -15,0 0,2.5 0,7.5 -50,0 0,2.5 0,17.5 -100,0 0,2.5 0,17.5 -135,0 0,-37.5 0,-2.5 -10,0 0,-7.49805 -2.5,0 0,7.49805 0,0.002 0,2.498 10,0 0,40 2.5,0 135,0 2.5,0 0,-20 97.5,0 2.5,0 0,-20 50,0 0,-2.5 0,-7.5 10,0 0,70 -320,0 0,-70 12.5,0 0,-2.5 -15,0 z"
					style="fill: #808080;" />
				</g>
				<g id="highlight">
				  <path style="fill: #ffffff;" d="m 2.5,1039.8622 10,0 0,10 -10,0 z" />
				  <path
					d="m 2.5,1039.8622 0,2.9199 2.919922,-2.9199 -2.919922,0 z m 6.455078,0 -6.455078,6.4551 0,3.5371 9.990234,-9.9922 -3.535156,0 z m 3.544922,3.5273 -6.472656,6.4727 3.535156,0 2.9375,-2.9375 0,-3.5352 z"
					style="fill: #000000;" />
				</g>
			  </g>
			</svg>
			<div id="elementNav" class="row text-center">
			  <a href="#a" class="underlineLink" id="previousElement">{previousElement}</a>&nbsp;&nbsp;←&nbsp; <span
				id="currentElement">{element.sym}</span>&nbsp;&nbsp;→&nbsp; <a class="underlineLink" id="nextElement">{nextElement}</a>
			</div>
		  </div>
		</div>
	  </div>
	</div>
  </div>
  
  <div class="footer">
	<Footer />
  </div>
  