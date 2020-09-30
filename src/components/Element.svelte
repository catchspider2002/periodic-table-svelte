<script>
  export let langValue, name, num, className;

  import Constants from "./constants.js";
  let constants = Constants[num];
</script>

<td id="ele{num - -1}" class="eleTD">
  <a href="{langValue}/{constants.nme}" id="element{num}" class="elements {className}">
    <div class="eleNum">{constants.num}</div>
    <div class="eleSym heavyFont">{constants.sym}</div>
    <div class="eleNm">{name}</div>
    <div class="eleWt">{constants.aWt}</div>
  </a>
</td>
