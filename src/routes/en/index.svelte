<script context="module">
  export function preload() {
    return this.fetch(`en.json`)
      .then((r) => r.json())
      .then((posts) => {
        return { posts };
      });
  }
</script>

<script>
  export let posts;
  import Lang from "./locale.js";
  import Nav from "./Nav.svelte";
  let langValue = Lang.lang;
</script>

<style>
  ul {
    margin: 0 0 1em 0;
    line-height: 1.5;
    color: black;
  }
</style>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<Nav/>
<h1>Recent posts - {Lang.homeTitle}</h1>

<ul>
  {#each posts as post}
    <!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
    <li><a rel="prefetch" href="{langValue}/{post.slug}">{post.title}</a></li>
  {/each}
  <a href="{langValue}/credits">Credits</a>
  <br /><br />
  <a href="{langValue}/store">Store</a><br /><br />
  <a href="{langValue}/compare">Compare</a><br /><br />
  <a href="{langValue}/privacy-policy">Privacy</a><br /><br />
  <a href="{langValue}/list">List</a><br /><br />
  <a href="{langValue}/printables">Printables</a><br /><br />
  <a href="{langValue}/translation">Translation</a><br /><br />
  <a href="{langValue}/about">About</a><br /><br />
  
</ul>
