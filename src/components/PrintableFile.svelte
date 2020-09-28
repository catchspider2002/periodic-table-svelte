<script>
  export let title, description, rating, languages, link, downloadLang, supported;
</script>

<style>
  a {
    margin: 0 auto;
    display: inline-flex;
    padding: 10px;
  }

  svg {
    margin-top: 5px;
  }
</style>

<div class="flex flex-col font-size-15 overflow-auto">
  <h1>{title}</h1>
  <img class="py-4 image" draggable="false" src="images/Marketing-Image-4.png" />
  <div class="py-4">{description}</div>
  <div class="py-2 padding-top-20 font-weight-600">{supported}</div>
  <div class="py-2 padding-top-10">{languages}</div>
  <div>⭐⭐⭐⭐⭐ ({rating})</div>
  <div class="py-2 padding-top-20 padding-bottom-20">
    <p />
    <!-- <button id="download4Button" class="mx-auto downloadButton justify-center content-center"> -->
    <a href={link} class="py-2 mx-auto downloadButton justify-center content-center">
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 512 512" stroke="currentColor" fill="currentColor">
        <path
          d="M272 397l-1 1c-1 0-1 1-1 1h-1c0 1-1 1-1 1s-1 0-1 1h-1s-1 0-1 1h-2c-1 0-1 1-1 1h-3-1-7-1s0-1-1-1h-1-1c0-1-1-1-1-1h-1c0-1-1-1-1-1s-1 0-1-1h-1s0-1-1-1l-1-1s0 0 0 0L131 288c-9-9-9-24 0-33s24-9 33 0l69 69V39c0-13 10-23 23-23s23 10 23 23v285l69-69c9-9 24-9 33 0s9 24 0 33zM23 248c13 0 24 11 24 24v178h418V272c0-13 11-24 24-24s23 11 23 24v201c0 13-10 23-23 23H23c-13 0-23-10-23-23V272c0-13 10-24 23-24z" />
      </svg>
      <span class="buttonLabel self-center">{downloadLang}</span></a>
  </div>
</div>
