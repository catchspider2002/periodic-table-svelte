<script>
  //   import Nav from "../components/Nav_old_delte.svelte";
  import Nav from "./_Nav.svelte";
  import Footer from "./_Footer.svelte";
  import { onMount } from "svelte";

  export let segment;
  //   console.log("Checking layout");

  onMount(async () => {
    let defaultNewTheme = localStorage.getItem("defaultNewTheme");

    if (!defaultNewTheme) {
      defaultNewTheme = "light";

      if (window.matchMedia("(prefers-color-scheme)").media !== "not all") {
        if (window.matchMedia("(prefers-color-scheme: dark)").matches) defaultNewTheme = "dark";
        else defaultNewTheme = "light";
      }

      localStorage.setItem("defaultNewTheme", defaultNewTheme);
    }
    console.log(localStorage.getItem("defaultNewTheme"));

    let defaultColor = localStorage.getItem("defaultColor");

    var invalidColors = [
      "color11",
      "color12",
      "color13",
      "color14",
      "color15",
      "color16",
      "color17",
      "color18",
      "color19",
      "color20",
      "color21",
      "color22",
      "color23",
      "color24",
      "color25",
    ];

    if (!defaultColor || invalidColors.indexOf(defaultColor) > -1) {
      // Added so that users already using invalidcolors are reset to color8
      localStorage.setItem("defaultColor", "color8");
      defaultColor = "color8";
    } else {
      if (defaultColor.indexOf(",") > 0) {
        localStorage.setItem("defaultColor", "color10");
        defaultColor = "color10";
      }
    }

    let defaultTemp = localStorage.getItem("defaultTemp");

    if (!defaultTemp) {
      localStorage.setItem("defaultTemp", "celsius");
      defaultTemp = "celsius";
    }

    let defaultStyle = localStorage.getItem("defaultStyle");

    if (!defaultStyle) {
      localStorage.setItem("defaultStyle", "1");
      defaultStyle = "1";
    }

    let defaultMargin = localStorage.getItem("defaultMargin");

    if (!defaultMargin) {
      localStorage.setItem("defaultMargin", "1");
      defaultMargin = "1";
    }

    setColor("253, 58, 74");
  });


  

function rgbToHex(rgb) {
  var r = rgb.split(",")[0];
  var g = rgb.split(",")[1];
  var b = rgb.split(",")[2];

  var rgbNew = b | (g << 8) | (r << 16);
  return "#" + (0x1000000 + rgbNew).toString(16).slice(1);
}

function colorLuminance(hex, lum) {

	// validate hex string
	hex = String(hex).replace(/[^0-9a-f]/gi, '');
	if (hex.length < 6) {
		hex = hex[0]+hex[0]+hex[1]+hex[1]+hex[2]+hex[2];
	}
	lum = lum || 0;

	// convert to decimal and change luminosity
	var rgb = "#", c, i;
	for (i = 0; i < 3; i++) {
		c = parseInt(hex.substr(i*2,2), 16);
		c = Math.round(Math.min(Math.max(0, c + (c * lum)), 255)).toString(16);
		rgb += ("00"+c).substr(c.length);
	}

	return rgb;
}

function setColor(color) {
  var hexValue = rgbToHex(color);
var root = document.documentElement;

  var darkerColor50 = colorLuminance(hexValue, -0.5);
  var darkerColor0 = colorLuminance(hexValue, -0.6);

  var metaThemeColor = document.querySelector("meta[name=theme-color]");
  metaThemeColor.setAttribute("content", darkerColor50);

  var metaTileColor = document.querySelector("meta[name=msapplication-TileColor]");
  metaTileColor.setAttribute("content", hexValue);
  
  root.style.setProperty("--theme-color", color);
  root.style.setProperty("--darker-color-50", darkerColor50);
  root.style.setProperty("--darker-color-0", darkerColor0);
  console.log("Darker color set")
}
</script>

<style>
  main {
    position: relative;
    /* max-width: 56em; */
    /* background-color: white; */
    /* padding: 2em; */
    /* margin: 0 auto; */
    box-sizing: border-box;
  }
</style>

<Nav />
<!-- <Nav {segment} /> -->

<main data-theme="dark">
  <slot />
</main>
<Footer/>