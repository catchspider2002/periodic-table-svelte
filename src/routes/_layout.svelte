<script>
  //   import Nav from "../components/Nav_old_delte.svelte";
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
  });
</script>

<style>
  main {
    position: relative;
    /* max-width: 56em; */
    background-color: white;
    /* padding: 2em; */
    /* margin: 0 auto; */
    box-sizing: border-box;
  }
</style>

<!-- <Nav {segment} /> -->

<main data-theme="light">
  <slot />
</main>
