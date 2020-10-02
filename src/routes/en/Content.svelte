<script>
  import { getContext } from "svelte";
  import Surprise from "./Surprise.svelte";
  export let name;

  const { open } = getContext("simple-modal");

  const showSurprise = () => {
    open(
      Surprise,
      { message: "It's a modal!" },
      {
        // closeButton: CloseButton,
        // styleBg: {
        //   background: "rgba(200, 255, 0, 0.66)",
        // },
        // styleWindow: {
        //   border: "2px solid #00beff",
        //   boxShadow: "inset 0 0 0 2px white, 0 0 0 2px white",
        //   background: "#ff7000",
        // },
        styleContent: {
          color: "white",
          padding: "0"
        },
        styleCloseButton: {
          color: "white",
          borderRadius: "4px",
          backgroundColor: "transparent",
          zIndex: "5",
        },
      }
    );
  };
</script>

<style>
</style>

<!-- <p><button on:click={showSurprise}>Show me a surprise!</button></p> -->
<a on:click={showSurprise}>
  <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
    <path
      d="M434 264v-4-4-4-4l61-38-38-90-69 16-12-12 16-69-90-38-38 61h-16l-38-61-90 38 16 69-12 12-69-16-38 90 61 38v16l-61 38 38 90 69-16 12 12-16 69 90 38 38-61h16l38 61 90-38-16-69 12-12 69 16 38-90zm-28-30c1 4 1 7 1 11 1 4 1 8 1 11 0 4 0 8-1 11 0 4 0 8-1 11l56 35-20 48-64-14c-5 6-10 11-15 16s-10 10-16 15l14 64-48 20-35-56c-4 1-7 1-11 1-4 1-7 1-11 1s-7 0-11-1c-4 0-8 0-11-1l-35 56-48-20 14-64c-6-5-11-10-16-15s-10-10-15-16l-64 14-20-48 56-35c-1-4-1-7-1-11-1-4-1-7-1-11s0-7 1-11c0-4 0-8 1-11l-56-35 20-48 64 14c5-6 10-11 15-16s10-10 16-15l-14-64 48-20 35 56c4-1 7-1 11-1 4-1 7-1 11-1s7 0 11 1c4 0 8 0 11 1l35-56 48 20-14 64c6 5 11 10 16 15s10 10 15 16l64-14 20 48zM256 344c12 0 24-2 34-7 11-4 20-11 28-19s15-17 19-28c5-10 7-22 7-34s-2-24-7-34c-4-11-11-20-19-28s-17-15-28-19c-10-5-22-7-34-7s-24 2-34 7c-11 4-20 11-28 19s-15 17-19 28c-5 10-7 22-7 34s2 24 7 34c4 11 11 20 19 28s17 15 28 19c10 5 22 7 34 7zm0-150c9 0 17 2 24 5 8 3 14 8 20 13 5 6 10 12 13 20 3 7 5 15 5 24s-2 17-5 24c-3 8-8 14-13 20-6 5-12 10-20 13-7 3-15 5-24 5s-17-2-24-5c-8-3-14-8-20-13-5-6-10-12-13-20-3-7-5-15-5-24s2-17 5-24c3-8 8-14 13-20 6-5 12-10 20-13 7-3 15-5 24-5z" />
  </svg>{name}</a>
