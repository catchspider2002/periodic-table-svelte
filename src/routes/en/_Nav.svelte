<style>
  :global(.content){
      padding: 0;
  }
  .toggle,
  [id^="drop"] {
    display: none;
  }

  /* Giving a background-color to the nav container. */
  nav {
    margin: 0;
    padding: 0;
    background-color: var(--darker-color-50);
    position: sticky;
    top: 0;
    text-transform: uppercase;
    z-index: 5;
    /* height: 52px; */
  }

  #logo {
    display: inline-flex;
    place-items: center;
    line-height: 1;
    gap: 0.5em;
    /*     padding: 0 30px; */
    margin-right: auto;
  }

  /* Since we'll have the "ul li" "float:left"
 * we need to add a clear after the container. */

  nav:after {
    content: "";
    display: table;
    clear: both;
    /* 		float: left; */
  }

  /* Removing padding, margin and "list-style" from the "ul",
 * and adding "position:reltive" */
  nav ul {
    float: right;
    padding: 0;
    margin: 0;
    list-style: none;
    position: relative;
  }

  /* Positioning the navigation items inline */
  nav ul li {
    margin: 0px;
    display: inline-block;
    float: left;
    /* background-color: #254441; */
  }

  nav a {
    display: block;
    padding: 0.5em 1em;
    color: #fff;
    font-size: 0.9em;
    text-decoration: none;
  }
  nav ul li a {
    display: grid;
    grid-template-columns: auto 1fr;
    padding: 13px 15px;
    margin: 0 0.25em;
    gap: 0.75em;
    cursor: pointer;
  }

  nav ul li ul li:hover {
    background: #000000;
  }

  /* Background color change on Hover */
  nav a:hover {
    background-color: #000000;
  }

  /* Hide Dropdowns by Default
 * and giving it a position of absolute */
  nav ul ul {
    display: none;
    position: absolute;
    /* has to be the same number as the "line-height" of "nav a" */
    /*     top: 60px; */
  }

  /* Display Dropdowns on Hover */
  nav ul li:hover > ul {
    display: inherit;
  }

  /* Fisrt Tier Dropdown */
  nav ul ul li {
    width: 170px;
    float: none;
    display: list-item;
    position: relative;
  background-color: var(--darker-color-50);
  }

  /* Second, Third and more Tiers	
 * We move the 2nd and 3rd etc tier dropdowns to the left
 * by the amount of the width of the first tier.
*/
  nav ul ul ul li {
    position: relative;
    top: -60px;
    left: 170px;
  }

  /* Media Queries
--------------------------------------------- */

  @media all and (max-width: 768px) {
    nav {
      /*       margin: 0; */
      display: grid;
      grid-template-columns: auto 1fr;
      z-index: 2;
    }

    /* Hide the navigation menu by default */
    /* Also hide the  */
    .toggle + a,
    .menu {
      display: none;
    }

    .menu {
      grid-column: 1 / span 2;
    }

    .toggle {      
    display: grid;
    grid-template-columns: auto 1fr;
    padding: 13px 15px;
/*     margin: 0 0.25em; */
    gap: 0.75em;
/*       background-color: #254441; */
      color: #fff;
      font-size: 0.9em;
/*       text-decoration: none; */
/*       border: none; */
      margin-left: auto;
    }
		
		.burger{
    	gap: 0;
		}

    .toggle:hover {
      background-color: #000000;
    }

    /* Display Dropdown when clicked on Parent Lable */
    [id^="drop"]:checked + ul {
      display: block;
    }

    /* Change menu item's width to 100% */
    nav ul li {
      display: block;
      width: 100%;
    }
    nav ul li a {
      margin: 0;
      /*     gap: 0.75em; */
    }

    nav ul ul .toggle,
    nav ul ul a {
      padding: 0 40px;
    }

    nav ul ul ul a {
      padding: 0 80px;
    }

    nav a:hover,
    nav ul ul ul a {
      background-color: #000000;
    }

    nav ul li ul li .toggle,
    nav ul ul a,
    nav ul ul ul a {
      padding: 14px 20px;
      color: #fff;
      font-size: 0.9em;
    }

    nav ul li ul li .toggle,
    nav ul ul a {
      background-color: #212121;
    }

    /* Hide Dropdowns by Default */
    nav ul ul {
      float: none;
      position: static;
      color: #ffffff;
      /* has to be the same number as the "line-height" of "nav a" */
    }

    /* Hide menus on hover */
    nav ul ul li:hover > ul,
    nav ul li:hover > ul {
      display: none;
    }

    /* Fisrt Tier Dropdown */
    nav ul ul li {
      display: block;
      width: 100%;
    }

    nav ul ul ul li {
      position: static;
      /* has to be the same number as the "width" of "nav ul ul li" */
    }
  }

  @media all and (max-width: 330px) {
    nav ul li {
      display: block;
      width: 94%;
    }
  }
</style>

<nav>
  <a id="logo" class="navbar-brand" href={langValue} aria-label="Home">
    {@html logoIcon}PERIODIC-TABLE.IO
  </a>

  <label for="drop" class="toggle burger"><svg
      xmlns="http://www.w3.org/2000/svg"
      width="22"
      height="22"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      fill="none"
      stroke-linecap="round"
      stroke-linejoin="round">
      <path stroke="none" d="M0 0h24v24H0z" fill="none" />
      <line x1="4" y1="6" x2="20" y2="6" />
      <line x1="4" y1="12" x2="20" y2="12" />
      <line x1="4" y1="18" x2="20" y2="18" />
    </svg></label>
  <input type="checkbox" id="drop" />
  <ul class="menu">
    <li>
      <a href="{langValue}/list">
       {@html listIcon}{Lang.list}</a>
    </li>
    <li>
      <a href="{langValue}/compare">
        {@html compareIcon}{Lang.compare}</a>
    </li>
    <li>
      <label for="drop-1" class="toggle">
      {@html tablesIcon}Tables +</label>
      <a>
        {@html tablesIcon}Tables ▼</a>
      <input type="checkbox" id="drop-1" />
      <ul>
        <li><a href="#a">Solubility Chart</a></li>
        <li><a href="#a">Reactivity Series</a></li>
      </ul>
    </li>
    <li>
      <a href="{langValue}/printables">
        {@html printablesIcon}{Lang.printables}</a>
    </li>
    <li>
      <a href="{langValue}/store">
        {@html storeIcon}{Lang.store}</a>
    </li>
    <li>
      <a href="{langValue}/translation">
        {@html translationIcon}{Lang.translation}</a>
    </li>
    <li>
      <Modal>
        <Content name={Lang.settings} />
      </Modal>
    </li>
    <li>
      <a on:click={() => changeTheme()}>
        <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          {#if theme === light}
            <path transition:fly={{ y: 200, duration: 600 }} d={theme} />
          {:else}
            <path transition:fly={{ y: -200, duration: 600 }} d={theme} />
          {/if}
        </svg>{Lang.theme}
      </a>
    </li>
  </ul>
</nav>
<script>
  import { fly } from "svelte/transition";
  import Lang from "./locale.js";
  let langValue = Lang.lang;
  import Content from "./_Content.svelte";
  import Modal from "svelte-simple-modal";
  
  let svgHeader = "<svg xmlns='http://www.w3.org/2000/svg' width='22' height='22' viewBox='0 0 512 512' stroke='currentColor' fill='currentColor'><path d='"
  let svgFooter = "' /></svg>"

	let logoIcon = '<svg xmlns="http://www.w3.org/2000/svg" width="38" height="38" viewBox="0 0 10.054 10.054" class="periodic-table-logo" fill="#fff"><path d="M3.146 1.905a1.301 1.301 0 00-1.301 1.301 1.301 1.301 0 001.009 1.266 1.596 1.596 0 011.553-1.581 1.301 1.301 0 00-1.261-.986zm4.841 1.581a1.508 1.508 0 00-1.47 1.178l-.824-.1a.126.126 0 00-.14.11.126.126 0 00.11.14l.821.1a1.508 1.508 0 00-.004.081 1.508 1.508 0 001.508 1.508 1.508 1.508 0 001.508-1.508 1.508 1.508 0 00-1.508-1.508zm-4.331 1.69a.126.126 0 00-.078.028l-.843.683a1.301 1.301 0 00-.874-.34A1.301 1.301 0 00.56 6.848a1.301 1.301 0 001.301 1.301 1.301 1.301 0 001.301-1.301 1.301 1.301 0 00-.257-.774l.832-.674a.126.126 0 00.019-.177.126.126 0 00-.099-.047z"/><path d="M4.45 2.978a1.508 1.508 0 00-1.508 1.508 1.508 1.508 0 00.297.895l.292-.237a.201.201 0 01.283.03.201.201 0 01-.03.283l-.265.215a1.508 1.508 0 00.931.322 1.508 1.508 0 001.444-1.077l-.241-.029a.201.201 0 01-.175-.224.201.201 0 01.224-.175l.255.031a1.508 1.508 0 00.002-.034 1.508 1.508 0 00-1.508-1.508z" opacity=".7"/></svg>';
	
	let listIcon = svgHeader + "M23 358v-87h87v87zm29-58v29h29v-29zm-29-59v-87h87v87zm29-58v29h29v-29zm-29-58V37h87v88zm29-58v29h29V67zm117 145v-29h262v29zm204 88v29H169v-29zM169 67h320v29H169zM23 475v-88h87v88zm29-59v29h29v-29zm117 29v-29h262v29z" + svgFooter;
    
	let compareIcon = svgHeader + "M508 276l-70-70c-3-2-7-4-11-4H322c-22 0-40 18-40 40v230c0 22 18 40 40 40h150c22 0 40-18 40-40V287c0-4-2-8-4-11zm-66-23l19 19h-19zm30 229H322c-6 0-10-4-10-10V242c0-6 4-10 10-10h90v55c0 8 7 15 15 15h55v170c0 6-4 10-10 10zM156 4c-3-2-7-4-11-4H40C18 0 0 18 0 40v230c0 22 18 40 40 40h150c22 0 40-18 40-40V85c0-4-2-8-4-11zm4 47l19 19h-19zm30 229H40c-6 0-10-4-10-10V40c0-6 4-10 10-10h90v55c0 8 7 15 15 15h55v170c0 6-4 10-10 10zm136-174c3 3 7 4 11 4s8-1 11-4c5-6 5-16 0-22l-15-14h4c47 0 85 38 85 85 0 8 7 15 15 15s15-7 15-15c0-63-52-115-115-115h-4l15-14c5-6 5-16 0-22-6-5-16-5-22 0l-40 40c-5 6-5 16 0 22zM186 406c-6-5-16-5-22 0-5 6-5 16 0 22l15 14h-4c-47 0-85-38-85-85 0-8-7-15-15-15s-15 7-15 15c0 63 52 115 115 115h4l-15 14c-5 6-5 16 0 22 3 3 7 4 11 4s8-1 11-4l40-40c5-6 5-16 0-22zm251-74h-80c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15zm0 60h-80c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15zM155 130H75c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15zm0 60H75c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15z" + svgFooter;
    
    let tablesIcon = svgHeader + "M195.75 15v482M15 195.75h482M75.25 15h361.5C470.128 15 497 41.872 497 75.25v361.5c0 33.378-26.872 60.25-60.25 60.25H75.25C41.872 497 15 470.128 15 436.75V75.25C15 41.872 41.872 15 75.25 15z' fill='none' stroke-width='30" + svgFooter;
	
    let printablesIcon = svgHeader + "M480 113h-32l-35-57c-3-4-8-7-13-7h-41V15c0-8-7-15-15-15H168c-8 0-15 7-15 15v34h-41c-5 0-10 3-13 7l-35 57H32c-8 0-15 7-15 15v256c0 8 7 15 15 15h97v98c0 8 7 15 15 15h224c8 0 15-7 15-15v-98h97c8 0 15-7 15-15V128c0-8-7-15-15-15zm-88-34l21 34h-54V79zM183 30h146v83H183zm-63 49h33v34H99zm233 403H159V335h194zm112-113h-82v-34h17c8 0 15-7 15-15s-7-15-15-15H112c-8 0-15 7-15 15s7 15 15 15h17v34H47V143h418zm-50-180c-2-8-11-14-19-11-8 2-13 10-10 18 2 9 11 13 18 10 8-2 12-10 11-17z" + svgFooter;
	
    let storeIcon = svgHeader + "M.659 233.105c0-1 42-112 43-117 0 0 0 0 0 0 9-22 23-40 42-54 25-18 118-45 178-43 52 2 136 24 162 43 19 14 34 32 42 54 46 123 43 116 44 118 0 3 0 7-2 10-2 4-5 7-9 8l-95 24v199c0 9-7 16-15 16h-269c-9 0-15-7-15-16v-199l-95-24c-5-1-8-4-10-8-2-3-2-7-1-11zm106 12v-16l-67-15c-1 4-3 9-4 13 24 6 53 13 71 18zm97-190c1 27 24 50 52 50s51-23 53-50c-39-7-64-8-105 0zm235 72c-6-16-16-30-30-40-9-7-37-17-70-26-5 42-40 74-83 74s-78-32-82-74c-34 9-62 19-70 26-14 10-25 24-31 40v0c-1 3-12 31-22 58l56 13v-55c0-8 6-15 15-15 8 0 15 7 15 15v263h238v-263c0-8 7-15 15-15 9 0 16 7 16 15v55l55-13zm33 87l-66 15v16l71-18zm-335 246h238v-24h-238z" + svgFooter;
	
    let translationIcon = svgHeader + "M511 347l-25-69c17-27 26-59 26-92 0-95-77-172-172-172-88 0-160 65-171 149H15c-8 0-15 7-15 15v305c0 5 3 10 8 13 2 1 4 2 7 2s5-1 8-2l90-52h198c8 0 15-7 15-15v-71c4 1 9 1 14 1 27 0 55-7 79-20l73 27c1 1 3 1 5 1 4 0 8-1 11-4 4-4 5-11 3-16zm-215 67H109c-3 0-6 1-8 2l-71 41V193h137c1 24 7 47 16 67h-17v-5c0-9-7-15-15-15s-15 6-15 15v5H93c-8 0-15 7-15 15s7 15 15 15h70l-11 14-3-4c-5-7-15-8-21-3-7 5-8 15-3 21l7 10-30 37c-5 6-4 15 2 21 3 2 7 3 10 3 4 0 9-2 12-6l25-31 16 21c3 3 8 5 12 5 3 0 7-1 9-3 7-5 8-14 3-21l-20-26 29-36 2-2v0c23 31 56 53 94 63zm159-133l17 46-49-18c-4-2-8-1-12 1-22 12-46 19-71 19-79 0-143-64-143-143 0-78 64-142 143-142 78 0 142 64 142 142 0 30-9 58-25 82-3 4-4 9-2 13zM353 108c-3-5-8-9-14-9 0 0 0 0 0 0-6 0-11 4-14 9l-60 133c-4 7-1 16 7 20 8 3 16 0 20-8l16-36h62l16 37c3 5 8 9 14 9 2 0 4-1 6-2 8-3 11-12 8-20zm-31 79l17-37 17 37z" + svgFooter;
	
  let dark =
    "M406.17 372.075c-10 2-21 3-31 3-35 0-67-9-97-26-29-17-52-40-70-70-17-29-25-61-25-96 0-37 10-71 29-102-38 11-69 33-93 65-25 32-37 69-37 110 0 25 5 48 15 71 9 23 22 42 39 58 16 17 35 30 58 39 23 10 46 15 71 15 27 0 53-6 78-18 25-11 46-28 63-49zm58-24c-18 39-45 70-81 93s-75 34-118 34c-30 0-58-5-85-17s-51-27-70-47c-20-19-35-43-47-70s-17-55-17-85c0-29 5-57 16-84 11-26 26-49 45-69 18-19 41-35 67-47 26-11 54-18 83-19 8-1 14 3 17 11 4 8 2 15-4 21-17 14-29 32-38 51-8 20-13 41-13 63 0 28 7 54 21 78s33 43 57 56c24 14 50 21 78 21 22 0 44-5 65-14 8-4 15-2 20 3 3 3 5 6 5 10 1 4 1 8-1 11z";
  let light =
    "M384 256c0 35-14 67-37 91-24 23-56 37-91 37-35 0-67-14-91-37-23-24-37-56-37-91 0-35 14-67 37-91 24-23 56-37 91-37 35 0 67 14 91 37 23 24 37 56 37 91z m-43 0c0-24-9-45-25-60-15-16-36-25-60-25-24 0-45 9-60 25-16 15-25 36-25 60 0 24 9 45 25 60 15 16 36 25 60 25 24 0 45-9 60-25 16-15 25-36 25-60z m-106 235l0-43c0-12 9-21 21-21 12 0 21 9 21 21l0 43c0 11-9 21-21 21-12 0-21-10-21-21z m0-427l0-43c0-11 9-21 21-21 12 0 21 10 21 21l0 43c0 12-9 21-21 21-12 0-21-9-21-21z m-160 343l30-30c9-9 22-9 30 0 9 8 9 21 0 30l-30 30c-8 8-22 8-30 0-8-8-8-22 0-30z m302-302l30-30c8-8 22-8 30 0 8 8 8 22 0 30l-30 30c-9 9-22 9-30 0-9-8-9-21 0-30z m-356 130l43 0c12 0 21 9 21 21 0 12-9 21-21 21l-43 0c-11 0-21-9-21-21 0-12 10-21 21-21z m427 0l43 0c11 0 21 9 21 21 0 12-10 21-21 21l-43 0c-12 0-21-9-21-21 0-12 9-21 21-21z m-343-160l30 30c9 9 9 22 0 30-8 9-21 9-30 0l-30-30c-8-8-8-22 0-30 8-8 22-8 30 0z m302 302l30 30c8 8 8 22 0 30-8 8-22 8-30 0l-30-30c-9-9-9-22 0-30 8-9 21-9 30 0z";
  let theme = dark;

  function changeTheme() {
    theme = theme === dark ? light : dark;
  }
  function id(text) {
    return document.getElementById(text);
  }
</script>