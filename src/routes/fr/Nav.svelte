<script>
  import Lang from "./locale.js";
  let langValue = Lang.lang;
  import LangDropdown from "../../components/LanguageDropdown.svelte";
</script>

<style>
  a {
    color: #fff;
  }

  .toggle,
  [id^="drop"] {
    display: none;
  }

  /* Giving a background-color to the nav container. */
  nav {
    margin: 0;
    padding: 0;
    background-color: #254441;
    position: sticky;
    top: 0;
    /* width: 100%; */
  }

  #logo {
    display: block;
    padding: 0 30px;
    /* float: left; */
    /* font-size: 20px; */
    /* line-height: 60px; */
    margin-right: auto;
  }

  /* Since we'll have the "ul li" "float:left"
 * we need to add a clear after the container. */

  nav:after {
    content: "";
    display: table;
    clear: both;
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
    background-color: #254441;
  }

  /* Styling the links */
  nav a {
    display: block;
    padding: 0.75em 1em;
    color: #fff;
    font-size: 17px;
    text-decoration: none;
  }
  nav ul li a {
    display: flex;
    gap: 0.5em;
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
    top: 60px;
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
  }

  /* Second, Third and more Tiers	
 * We move the 2nd and 3rd etc tier dropdowns to the left
 * by the amount of the width of the first tier.
*/
  nav ul ul ul li {
    position: relative;
    top: -60px;
    /* has to be the same number as the "width" of "nav ul ul li" */
    left: 170px;
  }

  /* Change ' +' in order to change the Dropdown symbol */
  li > a:after {
    content: " +";
  }
  li > a:only-child:after {
    content: "";
  }

  /* Media Queries
--------------------------------------------- */

  @media all and (max-width: 768px) {
    #logo {
      /* display: block; */
      padding: 0;
      /* width: 100%; */
      /* text-align: center; */
      /* float: none; */
    }

    nav {
      margin: 0;
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

    /* Stylinf the toggle lable */
    .toggle {
      display: block;
      background-color: #254441;
      padding: 14px 20px;
      color: #fff;
      font-size: 17px;
      text-decoration: none;
      border: none;
      margin-left: auto;
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
      font-size: 17px;
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
  <a id="logo" class="navbar-brand" href="./" aria-label="Home">
    <svg xmlns="http://www.w3.org/2000/svg" width="38" height="38" viewBox="0 0 10.054166 10.054166" class="periodic-table-logo">
      <g transform="translate(-11.223271,-248.751622)" style="fill:#ffffff">
        <path
          d="m 14.368697,250.65729 a 1.3007583,1.300758 0 0 0
          -1.300758,1.30076 1.3007583,1.300758 0 0 0 1.009148,1.26637
          1.5960997,1.5960997 0 0 1 1.552505,-1.58069 1.3007583,1.300758 0 0 0
          -1.260895,-0.98644 z m 4.841172,1.58093 a 1.5081255,1.5081255 0 0 0
          -1.470202,1.17775 l -0.824437,-0.0999 a 0.12567713,0.12567713 0 0 0
          -0.139889,0.10965 0.12567713,0.12567713 0 0 0 0.109624,0.13989 l
          0.820853,0.0995 a 1.5081255,1.5081255 0 0 0 -0.0041,0.0812
          1.5081255,1.5081255 0 0 0 1.508126,1.50813 1.5081255,1.5081255 0 0 0
          1.508125,-1.50813 1.5081255,1.5081255 0 0 0 -1.508125,-1.50812 z m
          -4.331148,1.68937 a 0.12567712,0.12567712 0 0 0 -0.07784,0.028 l
          -0.843043,0.68281 a 1.3007583,1.300758 0 0 0 -0.87434,-0.3398
          1.3007583,1.300758 0 0 0 -1.300758,1.30076 1.3007583,1.300758 0 0 0
          1.300758,1.30076 1.3007583,1.300758 0 0 0 1.300759,-1.30076
          1.3007583,1.300758 0 0 0 -0.257418,-0.77439 l 0.832219,-0.67406 a
          0.12567712,0.12567712 0 0 0 0.01858,-0.17676 0.12567712,0.12567712 0
          0 0 -0.09892,-0.0466 z" />
        <path
          d="m 15.672524,251.73018 a 1.5081255,1.5081254 0 0 0
          -1.508126,1.50813 1.5081255,1.5081254 0 0 0 0.296741,0.89542 l
          0.292273,-0.23672 a 0.20108339,0.20108339 0 0 1 0.282822,0.0297
          0.20108339,0.20108339 0 0 1 -0.0297,0.28282 l -0.2651,0.21471 a
          1.5081255,1.5081254 0 0 0 0.931091,0.32219 1.5081255,1.5081254 0 0 0
          1.444403,-1.07677 l -0.241045,-0.0292 a 0.20108339,0.20108339 0 0 1
          -0.175408,-0.22384 0.20108339,0.20108339 0 0 1 0.223814,-0.17541 l
          0.254668,0.0309 a 1.5081255,1.5081254 0 0 0 0.0017,-0.0337
          1.5081255,1.5081254 0 0 0 -1.508125,-1.50813 z"
          style="opacity:0.7" />
      </g>
    </svg>
  </a>

  <label for="drop" class="toggle"><svg
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
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
    <li><a href={langValue}>Home</a></li>
    <li>
      <a href="{langValue}/list">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M23 358v-87h87v87zm29-58v29h29v-29zm-29-59v-87h87v87zm29-58v29h29v-29zm-29-58V37h87v88zm29-58v29h29V67zm117 145v-29h262v29zm204 88v29H169v-29zM169 67h320v29H169zM23 475v-88h87v88zm29-59v29h29v-29zm117 29v-29h262v29z" />
        </svg>
        {Lang.list}</a>
    </li>
    <li>
      <a href="{langValue}/compare">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M508 276l-70-70c-3-2-7-4-11-4H322c-22 0-40 18-40 40v230c0 22 18 40 40 40h150c22 0 40-18 40-40V287c0-4-2-8-4-11zm-66-23l19 19h-19zm30 229H322c-6 0-10-4-10-10V242c0-6 4-10 10-10h90v55c0 8 7 15 15 15h55v170c0 6-4 10-10 10zM156 4c-3-2-7-4-11-4H40C18 0 0 18 0 40v230c0 22 18 40 40 40h150c22 0 40-18 40-40V85c0-4-2-8-4-11zm4 47l19 19h-19zm30 229H40c-6 0-10-4-10-10V40c0-6 4-10 10-10h90v55c0 8 7 15 15 15h55v170c0 6-4 10-10 10zm136-174c3 3 7 4 11 4s8-1 11-4c5-6 5-16 0-22l-15-14h4c47 0 85 38 85 85 0 8 7 15 15 15s15-7 15-15c0-63-52-115-115-115h-4l15-14c5-6 5-16 0-22-6-5-16-5-22 0l-40 40c-5 6-5 16 0 22zM186 406c-6-5-16-5-22 0-5 6-5 16 0 22l15 14h-4c-47 0-85-38-85-85 0-8-7-15-15-15s-15 7-15 15c0 63 52 115 115 115h4l-15 14c-5 6-5 16 0 22 3 3 7 4 11 4s8-1 11-4l40-40c5-6 5-16 0-22zm251-74h-80c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15zm0 60h-80c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15zM155 130H75c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15zm0 60H75c-8 0-15 7-15 15s7 15 15 15h80c8 0 15-7 15-15s-7-15-15-15z" />
        </svg>
        {Lang.compare}</a>
    </li>
    <li>
      <label for="drop-1" class="toggle">Tables +</label>
      <a href="#a">Tables</a>
      <input type="checkbox" id="drop-1" />
      <ul>
        <li><a href="#a">Solubility Chart</a></li>
        <li><a href="#a">Reactivity Series</a></li>
        <li><a href="#a">Tutorials</a></li>
      </ul>
    </li>
    <li>
      <a href="{langValue}/printables">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M480 113h-32l-35-57c-3-4-8-7-13-7h-41V15c0-8-7-15-15-15H168c-8 0-15 7-15 15v34h-41c-5 0-10 3-13 7l-35 57H32c-8 0-15 7-15 15v256c0 8 7 15 15 15h97v98c0 8 7 15 15 15h224c8 0 15-7 15-15v-98h97c8 0 15-7 15-15V128c0-8-7-15-15-15zm-88-34l21 34h-54V79zM183 30h146v83H183zm-63 49h33v34H99zm233 403H159V335h194zm112-113h-82v-34h17c8 0 15-7 15-15s-7-15-15-15H112c-8 0-15 7-15 15s7 15 15 15h17v34H47V143h418zm-50-180c-2-8-11-14-19-11-8 2-13 10-10 18 2 9 11 13 18 10 8-2 12-10 11-17z" />
        </svg>{Lang.printables}</a>
    </li>
    <li>
      <a href="{langValue}/store">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M.659 233.105c0-1 42-112 43-117 0 0 0 0 0 0 9-22 23-40 42-54 25-18 118-45 178-43 52 2 136 24 162 43 19 14 34 32 42 54 46 123 43 116 44 118 0 3 0 7-2 10-2 4-5 7-9 8l-95 24v199c0 9-7 16-15 16h-269c-9 0-15-7-15-16v-199l-95-24c-5-1-8-4-10-8-2-3-2-7-1-11zm106 12v-16l-67-15c-1 4-3 9-4 13 24 6 53 13 71 18zm97-190c1 27 24 50 52 50s51-23 53-50c-39-7-64-8-105 0zm235 72c-6-16-16-30-30-40-9-7-37-17-70-26-5 42-40 74-83 74s-78-32-82-74c-34 9-62 19-70 26-14 10-25 24-31 40v0c-1 3-12 31-22 58l56 13v-55c0-8 6-15 15-15 8 0 15 7 15 15v263h238v-263c0-8 7-15 15-15 9 0 16 7 16 15v55l55-13zm33 87l-66 15v16l71-18zm-335 246h238v-24h-238z" />
        </svg>{Lang.store}</a>
    </li>
    <li>
      <LangDropdown />
    </li>
    <li>
      <a href="{langValue}/translation">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M511 347l-25-69c17-27 26-59 26-92 0-95-77-172-172-172-88 0-160 65-171 149H15c-8 0-15 7-15 15v305c0 5 3 10 8 13 2 1 4 2 7 2s5-1 8-2l90-52h198c8 0 15-7 15-15v-71c4 1 9 1 14 1 27 0 55-7 79-20l73 27c1 1 3 1 5 1 4 0 8-1 11-4 4-4 5-11 3-16zm-215 67H109c-3 0-6 1-8 2l-71 41V193h137c1 24 7 47 16 67h-17v-5c0-9-7-15-15-15s-15 6-15 15v5H93c-8 0-15 7-15 15s7 15 15 15h70l-11 14-3-4c-5-7-15-8-21-3-7 5-8 15-3 21l7 10-30 37c-5 6-4 15 2 21 3 2 7 3 10 3 4 0 9-2 12-6l25-31 16 21c3 3 8 5 12 5 3 0 7-1 9-3 7-5 8-14 3-21l-20-26 29-36 2-2v0c23 31 56 53 94 63zm159-133l17 46-49-18c-4-2-8-1-12 1-22 12-46 19-71 19-79 0-143-64-143-143 0-78 64-142 143-142 78 0 142 64 142 142 0 30-9 58-25 82-3 4-4 9-2 13zM353 108c-3-5-8-9-14-9 0 0 0 0 0 0-6 0-11 4-14 9l-60 133c-4 7-1 16 7 20 8 3 16 0 20-8l16-36h62l16 37c3 5 8 9 14 9 2 0 4-1 6-2 8-3 11-12 8-20zm-31 79l17-37 17 37z" />
        </svg>
        {Lang.translation}</a>
    </li>
    <li>
      <a href="{langValue}/settings">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M434 264v-4-4-4-4l61-38-38-90-69 16-12-12 16-69-90-38-38 61h-16l-38-61-90 38 16 69-12 12-69-16-38 90 61 38v16l-61 38 38 90 69-16 12 12-16 69 90 38 38-61h16l38 61 90-38-16-69 12-12 69 16 38-90zm-28-30c1 4 1 7 1 11 1 4 1 8 1 11 0 4 0 8-1 11 0 4 0 8-1 11l56 35-20 48-64-14c-5 6-10 11-15 16s-10 10-16 15l14 64-48 20-35-56c-4 1-7 1-11 1-4 1-7 1-11 1s-7 0-11-1c-4 0-8 0-11-1l-35 56-48-20 14-64c-6-5-11-10-16-15s-10-10-15-16l-64 14-20-48 56-35c-1-4-1-7-1-11-1-4-1-7-1-11s0-7 1-11c0-4 0-8 1-11l-56-35 20-48 64 14c5-6 10-11 15-16s10-10 16-15l-14-64 48-20 35 56c4-1 7-1 11-1 4-1 7-1 11-1s7 0 11 1c4 0 8 0 11 1l35-56 48 20-14 64c6 5 11 10 16 15s10 10 15 16l64-14 20 48zM256 344c12 0 24-2 34-7 11-4 20-11 28-19s15-17 19-28c5-10 7-22 7-34s-2-24-7-34c-4-11-11-20-19-28s-17-15-28-19c-10-5-22-7-34-7s-24 2-34 7c-11 4-20 11-28 19s-15 17-19 28c-5 10-7 22-7 34s2 24 7 34c4 11 11 20 19 28s17 15 28 19c10 5 22 7 34 7zm0-150c9 0 17 2 24 5 8 3 14 8 20 13 5 6 10 12 13 20 3 7 5 15 5 24s-2 17-5 24c-3 8-8 14-13 20-6 5-12 10-20 13-7 3-15 5-24 5s-17-2-24-5c-8-3-14-8-20-13-5-6-10-12-13-20-3-7-5-15-5-24s2-17 5-24c3-8 8-14 13-20 6-5 12-10 20-13 7-3 15-5 24-5z" />
        </svg></a>
    </li>
    <li>
      <a href="{langValue}/theme">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
          <path
            d="M511 347l-25-69c17-27 26-59 26-92 0-95-77-172-172-172-88 0-160 65-171 149H15c-8 0-15 7-15 15v305c0 5 3 10 8 13 2 1 4 2 7 2s5-1 8-2l90-52h198c8 0 15-7 15-15v-71c4 1 9 1 14 1 27 0 55-7 79-20l73 27c1 1 3 1 5 1 4 0 8-1 11-4 4-4 5-11 3-16zm-215 67H109c-3 0-6 1-8 2l-71 41V193h137c1 24 7 47 16 67h-17v-5c0-9-7-15-15-15s-15 6-15 15v5H93c-8 0-15 7-15 15s7 15 15 15h70l-11 14-3-4c-5-7-15-8-21-3-7 5-8 15-3 21l7 10-30 37c-5 6-4 15 2 21 3 2 7 3 10 3 4 0 9-2 12-6l25-31 16 21c3 3 8 5 12 5 3 0 7-1 9-3 7-5 8-14 3-21l-20-26 29-36 2-2v0c23 31 56 53 94 63zm159-133l17 46-49-18c-4-2-8-1-12 1-22 12-46 19-71 19-79 0-143-64-143-143 0-78 64-142 143-142 78 0 142 64 142 142 0 30-9 58-25 82-3 4-4 9-2 13zM353 108c-3-5-8-9-14-9 0 0 0 0 0 0-6 0-11 4-14 9l-60 133c-4 7-1 16 7 20 8 3 16 0 20-8l16-36h62l16 37c3 5 8 9 14 9 2 0 4-1 6-2 8-3 11-12 8-20zm-31 79l17-37 17 37z" />
        </svg></a>
    </li>
  </ul>
</nav>
