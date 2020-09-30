<script>
  export let langValue, name, constants, className;
</script>

<a href="{langValue}/{constants.nme}" id="element1" class="elements {className}">
  <div class="eleNum">{constants.num}</div>
  <div class="eleSym heavyFont">{constants.sym}</div>
  <div class="eleNm">{name}</div>
  <div class="eleWt">{constants.aWt}</div>
</a>
