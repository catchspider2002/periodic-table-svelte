<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import Nav from "./_Nav.svelte";
  import PrintableFile from "../../components/PrintableFile.svelte";
</script>

<svelte:head>
  <script src="https://gumroad.com/js/gumroad-embed.js">
  </script>
</svelte:head>

<Nav />
<div class="content-wrapper">
  <div class="container">
    <div id="printablesHeader" class="row text-upper aboutHeader text-center heavyFont" />
    <div id="printablesLayout">
      <div class="grid-print">
        <PrintableFile
          title="Periodic Table poster #1 - Available in 35 languages"
          description="Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded table."
          rating="7 ratings"
          supported={Lang.languages}
          languages=" {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans}; {Lang.frTrans};
          {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans}; {Lang.nnTrans}; {Lang.plTrans};
          {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans}; {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans};
          {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};"
          image="Marketing-Image-1"
          link="https://gumroad.com/l/periodictableposter1/"
          downloadLang={Lang.download} />
        <PrintableFile
          title="Periodic Table poster #2 - Available in 35 languages"
          description="Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded table."
          rating="3 ratings"
          supported={Lang.languages}
          languages=" {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans}; {Lang.frTrans};
          {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans}; {Lang.nnTrans}; {Lang.plTrans};
          {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans}; {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans};
          {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};"
          image="Marketing-Image-2"
          link="https://gumroad.com/l/periodictableposter2/"
          downloadLang={Lang.download} />
        <PrintableFile
          title="Periodic Table poster #3 - Available in 35 languages"
          description="Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded table."
          rating="1 rating"
          supported={Lang.languages}
          languages=" {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans}; {Lang.frTrans};
          {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans}; {Lang.nnTrans}; {Lang.plTrans};
          {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans}; {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans};
          {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};"
          image="Marketing-Image-3"
          link="https://gumroad.com/l/periodictableposter3/"
          downloadLang={Lang.download} />
        <PrintableFile
          title="Periodic Table poster #4 - Available in 35 languages"
          description="Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded table."
          rating="1 rating"
          supported={Lang.languages}
          languages=" {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans}; {Lang.frTrans};
          {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans}; {Lang.nnTrans}; {Lang.plTrans};
          {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans}; {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans};
          {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};"
          image="Marketing-Image-4"
          link="https://gumroad.com/l/periodictableposter4/"
          downloadLang={Lang.download} />
      </div>
    </div>
  </div>
</div>

<Footer />