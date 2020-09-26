<script>
  import Nav from "../components/Nav.svelte";
  import { onMount } from "svelte";

  export let segment;
  console.log("Checking layout");

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

<Nav {segment} />

<main data-theme="light" >
  <slot />
</main>
