<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import PrintableFile from "../../components/PrintableFile.svelte";
  import Constants from "../../components/constants.js";
</script>

<svelte:head>
  <script src="https://gumroad.com/js/gumroad-embed.js">
  </script>
</svelte:head>

<div class="content-wrapper">
  <div class="container">
    <div id="printablesHeader" class="row text-upper aboutHeader text-center heavyFont" />
    <div id="printablesLayout">
      <div class="grid-print">
        <div class="flex flex-col font-size-15 overflow-auto">
          <h1>Periodic Table poster #1 - Available in 35 languages</h1>
          <img class="image" draggable="false" src="images/Marketing-Image-1.png" />
          <div class="padding-top-15">
            Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded
            table.
          </div>
          <div class="padding-top-20 font-weight-600">{Lang.languages}</div>
          <div class="padding-top-10">
            {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans};
            {Lang.frTrans}; {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans};
            {Lang.nnTrans}; {Lang.plTrans}; {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans};
            {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans}; {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};
          </div>
          <div class="padding-top-20 padding-bottom-20">
            <button id="download1Button" class="mx-auto downloadButton justify-center content-center">
              <span class="buttonImg self-center">y</span>
              <span class="buttonLabel font-size-15 font-weight-500 self-center">{Lang.download}</span>
            </button>
          </div>
        </div>
        <div class="flex flex-col font-size-15 overflow-auto">
          <h1>Periodic Table poster #2 - Available in 35 languages</h1>
          <img class="image" draggable="false" src="images/Marketing-Image-2.png" />
          <div class="padding-top-15">
            Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded
            table.
          </div>
          <div class="padding-top-20 font-weight-600">{Lang.languages}</div>
          <div class="padding-top-10">
            {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans};
            {Lang.frTrans}; {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans};
            {Lang.nnTrans}; {Lang.plTrans}; {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans};
            {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans}; {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};
          </div>
          <div class="padding-top-20 padding-bottom-20">
            <button id="download2Button" class="mx-auto downloadButton justify-center content-center">
              <span class="buttonImg self-center">y</span>
              <span class="buttonLabel font-size-15 font-weight-500 self-center">{Lang.download}</span>
            </button>
          </div>
        </div>
        <PrintableFile
          title="Periodic Table poster #3 - Available in 35 languages"
          description="Periodic Table of the elements poster which shows atomic number, symbol, name and atomic weight for all 118 elements in a color-coded table."
          rating="1 rating"
          supported={Lang.languages}
          languages=" {Lang.enTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans}; {Lang.fiTrans}; {Lang.frTrans};
          {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans}; {Lang.jaTrans}; {Lang.koTrans}; {Lang.nlTrans}; {Lang.nnTrans}; {Lang.plTrans};
          {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans}; {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans}; {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans};
          {Lang.viTrans}; {Lang.zhTrans}; {Lang.chTrans};"
          link="https://gumroad.com/l/periodictableposter4/"
          downloadLang={Lang.download} />
      </div>
    </div>
  </div>
</div>

<div class="footer">
  <Footer />
</div>
