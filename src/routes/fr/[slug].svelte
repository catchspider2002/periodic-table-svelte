<script context="module">
	export async function preload({ params }) {
	  // the `slug` parameter is available because
	  // this file is called [slug].svelte
	  const res = await this.fetch(`fr/${params.slug}.json`);
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
	import Lang from "./locale.js";
  
	let num = post.num - 1;
  </script>
  
  <style>
	/*
		  By default, CSS is locally scoped to the component,
		  and any unused styles are dead-code-eliminated.
		  In this page, Svelte can't know which elements are
		  going to appear inside the {{{post.html}}} block,
		  so we have to use the :global(...) modifier to target
		  all elements inside .content
	  */
	.content :global(h2) {
	  font-size: 1.4em;
	  font-weight: 500;
	}
  
	.content :global(pre) {
	  background-color: #f9f9f9;
	  box-shadow: inset 1px 1px 5px rgba(0, 0, 0, 0.05);
	  padding: 0.5em;
	  border-radius: 2px;
	  overflow-x: auto;
	}
  
	.content :global(pre) :global(code) {
	  background-color: transparent;
	  padding: 0;
	}
  
	.content :global(ul) {
	  line-height: 1.5;
	}
  
	.content :global(li) {
	  margin: 0 0 0.5em 0;
	}
  </style>
  
  <svelte:head>
	<title>{post.title}</title>
  </svelte:head>
  
  <h1>{post.title}</h1>
  
  <div class="content">
	{@html post.reason}
	<br /><br />
	{@html post.history}
	<br /><br />
	{@html post.uses}
	<br /><br />
	{post.facts}
	<br /><br />
	{post.dangers}
	<br /><br />
  
	<div class="content-wrapper">
	  <div class="container">
		<div class="masonry">
		  <div class="flex-container row">
			<div class="flex-cell">
			  <div id="firstSquare" class="flex-item masonry-col flex flex-col">
				<div id="resultNumber" class="flex line-height-normal" />
				<div id="resultSymbol" class="text-center flex content-center justify-center line-height-normal">
				  <span id="resultSymbolInner" class="self-center" />
				</div>
			  </div>
			</div>
			<div class="flex-cell">
			  <div id="secondSquare" class="flex-item masonry-col grid">
				<div id="group" class="heavyFont">{Lang.group}</div>
				<div id="outputGroup">{Constants[num].grp}</div>
				<div id="period" class="heavyFont">{Lang.period}</div>
				<div id="outputPeriod">{Constants[num].prd}</div>
				<div id="block" class="heavyFont">{Lang.block}</div>
				<div id="outputBlock">{Constants[num].blk}</div>
			  </div>
			</div>
		  </div>
		  <!-- Protons, Electrons, Neutrons -->
		  <div class="box-content masonry-col">
			<div class="grid-3">
			  <div id="protons" class="new-table text-center heavyFont truncate" />
			  <div id="electrons" class="new-table text-center heavyFont truncate" />
			  <div id="neutrons" class="new-table text-center heavyFont truncate" />
			  <div id="outputProtons" class="text-center new-table font-size-1-5" />
			  <div id="outputElectrons" class="text-center new-table font-size-1-5" />
			  <div id="outputNeutrons" class="text-center new-table font-size-1-5" />
			</div>
		  </div>
		  <!-- General Prooperties -->
		  <div class="box-content masonry-col">
			<span id="labelGeneralProp" class="headerOutline text-upper heavyFont" />
			<div class="grid">
			  <div id="labelAtmNoMain" class="new-table heavyFont" />
			  <div id="outputAtmNoMain" class="new-table" />
			  <div id="labelAtmWtMain" class="new-table heavyFont" />
			  <div id="outputAtmWtMain" class="new-table" />
			  <div id="labelMassNum" class="new-table heavyFont" />
			  <div id="outputMassNum" class="new-table" />
			  <div id="labelCategoryMain" class="new-table heavyFont" />
			  <div id="outputCategoryMain" class="new-table" />
			  <div id="labelColorMain" class="new-table heavyFont" />
			  <div id="outputColorMain" class="new-table" />
			  <div id="labelRadioMain" class="new-table heavyFont" />
			  <div id="outputRadioMain" class="new-table" />
			  <div id="labelStructureMain" class="new-table heavyFont" />
			  <div id="outputStructureMain" class="new-table" />
			</div>
		  </div>
		  <!-- Name Reason -->
		  <div class="box-content text-center masonry-col">
			<div id="elementReasonMain" class="line-height-2" />
		  </div>
		  <!-- History -->
		  <div class="box-content masonry-col">
			<span id="history" class="headerOutline text-upper heavyFont" />
			<div id="elementHistoryMain" class="line-height-2" />
		  </div>
		  <!-- Electron Configuration -->
		  <div id="electronConf" class="box-content masonry-col">
			<div class="grid padding-bottom-25">
			  <div id="labelElectronsMain" class="new-table heavyFont" />
			  <div id="outputElectronsMain" class="new-table ltrText text-left" />
			  <div id="labelConfigMain" class="new-table heavyFont hyphen" />
			  <div id="outputConfigMain" class="new-table ltrText text-left" />
			</div>
			<!-- <div id="elementDiagram">
					  <canvas id="myCanvas"></canvas>
					</div> -->
			<!-- <svelte-electron num="118" sym="He" /> -->
		  </div>
		  <!-- Facts -->
		  <div class="box-content masonry-col text-center">
			<div id="elementFactsMain" class="line-height-2" />
		  </div>
		  <!-- Physical Properties -->
		  <div class="box-content masonry-col">
			<span id="labelPhysicalProp" class="headerOutline text-upper heavyFont" />
			<div class="grid">
			  <div class="new-table heavyFont" id="labelPhaseMain" />
			  <div id="outputPhaseMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelDensityMain" />
			  <div id="outputDensityMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelMeltingMain" />
			  <div id="outputMeltingMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelBoilingMain" />
			  <div id="outputBoilingMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelFusionMain" />
			  <div id="outputFusionMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelVaporizationMain" />
			  <div id="outputVaporizationMain" class="new-table" />
			  <div class="new-table heavyFont hyphen" id="labelSpecificMain" />
			  <div id="outputSpecificMain" class="new-table" />
			</div>
		  </div>
		  <!-- Abundance -->
		  <div class="box-content masonry-col">
			<div class="grid">
			  <div class="new-table heavyFont" id="labelCrustMain" />
			  <div id="outputCrustMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelUniverseMain" />
			  <div id="outputUniverseMain" class="new-table" />
			</div>
		  </div>
		  <!-- Image -->
		  <div class="masonry-col">
			<div class="blog-thumb"><img id="elementPic" src="images/placeholder.png" alt="" data-toggle="modal" data-target="#exampleModal" /></div>
			<div class="box-content bottom-rounded line-height-2">
			  <span id="imgCredits" class="heavyFont" /><span id="imgCreditsLink" />
			  <div id="imgDesc" />
			</div>
		  </div>
		  <!-- Identifiers -->
		  <div class="box-content masonry-col">
			<div class="grid">
			  <div class="new-table heavyFont" id="labelCASMain" />
			  <div id="outputCASMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelCIDMain" />
			  <div id="outputCIDMain" class="new-table" />
			</div>
		  </div>
		  <!-- Atomic Properties -->
		  <div class="box-content masonry-col">
			<span id="labelAtomicProp" class="headerOutline text-upper heavyFont" />
			<div class="grid">
			  <div class="new-table heavyFont" id="labelRadiusMain" />
			  <div id="outputRadiusMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelCovalentMain" />
			  <div id="outputCovalentMain" class="new-table" />
			  <div class="new-table heavyFont hyphen" id="labelElectronegativityMain" />
			  <div id="outputElectronegativityMain" class="new-table" />
			  <div class="new-table heavyFont hyphen" id="labelIonizationMain" />
			  <div id="outputIonizationMain" class="new-table" />
			  <div class="new-table heavyFont" id="labelVolumeMain" />
			  <div id="outputVolumeMain" class="new-table" />
			  <div class="new-table heavyFont hyphen" id="labelThermalMain" />
			  <div id="outputThermalMain" class="new-table" />
			  <div class="new-table heavyFont hyphen" id="labelOxidationMain" />
			  <div id="outputOxidationMain" class="new-table ltrText text-left" />
			</div>
		  </div>
		  <!-- Uses -->
		  <div class="box-content masonry-col">
			<span id="uses" class="headerOutline text-upper heavyFont" />
			<div id="elementUsesMain" class="line-height-2" />
			<div />
		  </div>
		  <!-- Hazards -->
		  <div class="box-content masonry-col text-center">
			<div id="elementDangersMain" class="line-height-2" />
		  </div>
		  <!-- Isotopes -->
		  <div class="box-content masonry-col">
			<span id="isotopes" class="headerOutline text-upper heavyFont" />
			<div class="heavyFont padding-0 margin-y-10" id="stableIsotopes" />
			<span id="stableIsotopesList" class="isotopeLine" />
			<div class="heavyFont padding-0 margin-y-10" id="unstableIsotopes" />
			<span id="unstableIsotopesList" class="isotopeLine" />
		  </div>
		  <!-- Important Links -->
		  <div class="box-content masonry-col">
			<span id="labelLinksMain" class="headerOutline text-upper heavyFont" />
			<div class="webLink"><a id="link1" class="underlineLink" target="_blank" rel="noopener noreferrer" /></div>
			<a id="link2" class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">Encyclopaedia Britannica</span></a>
			<a id="link3" class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">Wolfram Alpha</span></a>
			<a id="link4" class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">Chemicool</span></a>
			<a id="link5" class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">RSC Visual Elements</span></a>
			<a id="link6" class="webLink" target="_blank" rel="noopener noreferrer"><span class="underlineLink">WebElements</span></a>
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
			  <a class="underlineLink" id="previousElement" />&nbsp;&nbsp;←&nbsp; <span id="currentElement" />&nbsp;&nbsp;→&nbsp; <a
				class="underlineLink"
				id="nextElement" />
			</div>
		  </div>
		</div>
	  </div>
	</div>
  </div>
  