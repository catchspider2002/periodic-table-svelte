<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import Nav from "./Nav.svelte";
</script>

<Nav/>
<div class="content-wrapper">
  <div class="container">
    <div class="row text-upper aboutHeader text-center heavyFont">{Lang.privacy}</div>
    <div><span>{Lang.privacyFull}</span></div>
  </div>
</div>

<div class="footer">
  <Footer />
</div>
