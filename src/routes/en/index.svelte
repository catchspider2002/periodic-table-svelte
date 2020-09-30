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
  import Constants from "../../components/constants.js";
  import Element from "../../components/Element.svelte";
  import Lang from "./locale.js";
  import Nav from "./Nav.svelte";
  let langValue = Lang.lang;
</script>

<svelte:head>
  <title>Periodic-table.io</title>
</svelte:head>

<Nav />

<div id="headerwrap">
  <table id="ptable" class="table square margin-bottom-20">
    <tbody class="text-left">
      <tr class="text-center">
        <td id="groupPeriod" class="heavyFont"><span id="groupHeader">{Lang.group} →</span> <br /><span id="periodHeader">↓ {Lang.period}</span></td>
        <td id="group1" class="groups unselectable c1">1</td>
        <td id="group2" class="groups unselectable c2">2</td>
        <td id="group3" class="groups unselectable c3">3</td>
        <td id="group4" class="groups unselectable c4">4</td>
        <td id="group5" class="groups unselectable c5">5</td>
        <td id="group6" class="groups unselectable c6">6</td>
        <td id="group7" class="groups unselectable c7">7</td>
        <td id="group8" class="groups unselectable c8">8</td>
        <td id="group9" class="groups unselectable c9">9</td>
        <td id="group10" class="groups unselectable c10">10</td>
        <td id="group11" class="groups unselectable c11">11</td>
        <td id="group12" class="groups unselectable c12">12</td>
        <td id="group13" class="groups unselectable c13">13</td>
        <td id="group14" class="groups unselectable c14">14</td>
        <td id="group15" class="groups unselectable c15">15</td>
        <td id="group16" class="groups unselectable c16">16</td>
        <td id="group17" class="groups unselectable c17">17</td>
        <td id="group18" class="groups unselectable c18">18</td>
        <td id="group19" class="groups unselectable" />
      </tr>
      <tr>
        <td id="period1" class="periods unselectable r1 text-center">1</td>
        <td id="ele1" class="outerElement eleTD">
          <Element {langValue} name={Lang[Constants[0].nme]} constants={Constants[0]} className="otherNonmetals r1 c1" />
        </td>
        <td />
        <td id="snippetDetails" colspan="10" rowspan="3">
          <div class="innerSnippet">
            <div id="snippet" class="square">
              <div id="snippetNum" />
              <div id="snippetSym" class="text-center" />
              <div id="snippetWt" class="text-right" />
            </div>
            <div id="details" class="square text-left">
              <div id="detailRow1" class="heavyFont text-upper detailRow1" colspan="2" />
              <div id="detailRow2" />
              <div id="valueRow2" />
              <div id="detailRow3" />
              <div id="valueRow3" />
              <div id="detailRow4" />
              <div id="valueRow4" />
              <div id="detailRow5" />
              <div id="valueRow5" class="ltrText text-left" />
              <div id="detailRow6" />
              <div id="valueRow6" class="ltrText text-left" />
            </div>
          </div>
        </td>
        <td colspan="5" />
        <td id="ele2" class="outerElement eleTD">
          <Element {langValue} name={Lang[Constants[1].nme]} constants={Constants[1]} className="nobleGases r1 c18" />
        </td>
      </tr>
      <tr>
        <td id="period2" class="periods unselectable r2 text-center">2</td>
        <td id="ele3" class="eleTD">
          <Element {langValue} name={Lang[Constants[2].nme]} constants={Constants[2]} className="alkaliMetals r2 c1" />
        </td>
        <td id="ele4" class="eleTD">
          <Element {langValue} name={Lang[Constants[3].nme]} constants={Constants[3]} className="alkalineEarthMetals r2 c2" />
        </td>
        <td id="ele5" class="eleTD">
          <Element {langValue} name={Lang[Constants[4].nme]} constants={Constants[4]} className="metalloids r2 c13" />
        </td>
        <td id="ele6" class="eleTD">
          <Element {langValue} name={Lang[Constants[5].nme]} constants={Constants[5]} className="otherNonmetals r2 c14" />
        </td>
        <td id="ele7" class="eleTD">
          <Element {langValue} name={Lang[Constants[6].nme]} constants={Constants[6]} className="otherNonmetals r2 c15" />
        </td>
        <td id="ele8" class="eleTD">
          <Element {langValue} name={Lang[Constants[7].nme]} constants={Constants[7]} className="otherNonmetals r2 c16" />
        </td>
        <td id="ele9" class="eleTD">
          <Element {langValue} name={Lang[Constants[8].nme]} constants={Constants[8]} className="halogens r2 c17" />
        </td>
        <td id="ele10" class="eleTD">
          <Element {langValue} name={Lang[Constants[9].nme]} constants={Constants[9]} className="nobleGases r2 c18" />
        </td>
      </tr>
      <tr>
        <td id="period3" class="periods unselectable r3 text-center">3</td>
        <td id="ele11" class="eleTD">
          <Element {langValue} name={Lang[Constants[10].nme]} constants={Constants[10]} className="alkaliMetals r3 c1" />
        </td>
        <td id="ele12" class="eleTD">
          <Element {langValue} name={Lang[Constants[11].nme]} constants={Constants[11]} className="alkalineEarthMetals r3 c2" />
        </td>
        <td id="ele13" class="eleTD">
          <Element {langValue} name={Lang[Constants[12].nme]} constants={Constants[12]} className="postTransitionMetals r3 c13" />
        </td>
        <td id="ele14" class="eleTD">
          <Element {langValue} name={Lang[Constants[13].nme]} constants={Constants[13]} className="metalloids r3 c14" />
        </td>
        <td id="ele15" class="eleTD">
          <Element {langValue} name={Lang[Constants[14].nme]} constants={Constants[14]} className="otherNonmetals r3 c15" />
        </td>
        <td id="ele16" class="eleTD">
          <Element {langValue} name={Lang[Constants[15].nme]} constants={Constants[15]} className="otherNonmetals r3 c16" />
        </td>
        <td id="ele17" class="eleTD">
          <Element {langValue} name={Lang[Constants[16].nme]} constants={Constants[16]} className="halogens r3 c17" />
        </td>
        <td id="ele18" class="eleTD">
          <Element {langValue} name={Lang[Constants[17].nme]} constants={Constants[17]} className="nobleGases r3 c18" />
        </td>
      </tr>
      <tr>
        <td id="period4" class="periods unselectable r4 text-center">4</td>
        <td id="ele19" class="eleTD">
          <Element {langValue} name={Lang[Constants[18].nme]} constants={Constants[18]} className="alkaliMetals r4 c1" />
        </td>
        <td id="ele20" class="eleTD">
          <Element {langValue} name={Lang[Constants[19].nme]} constants={Constants[19]} className="alkalineEarthMetals r4 c2" />
        </td>
        <td id="ele21" class="eleTD">
          <Element {langValue} name={Lang[Constants[20].nme]} constants={Constants[20]} className="transitionMetals r4 c3" />
        </td>
        <td id="ele22" class="eleTD">
          <Element {langValue} name={Lang[Constants[21].nme]} constants={Constants[21]} className="transitionMetals r4 c4" />
        </td>
        <td id="ele23" class="eleTD">
          <Element {langValue} name={Lang[Constants[22].nme]} constants={Constants[22]} className="transitionMetals r4 c5" />
        </td>
        <td id="ele24" class="eleTD">
          <Element {langValue} name={Lang[Constants[23].nme]} constants={Constants[23]} className="transitionMetals r4 c6" />
        </td>
        <td id="ele25" class="eleTD">
          <Element {langValue} name={Lang[Constants[24].nme]} constants={Constants[24]} className="transitionMetals r4 c7" />
        </td>
        <td id="ele26" class="eleTD">
          <Element {langValue} name={Lang[Constants[25].nme]} constants={Constants[25]} className="transitionMetals r4 c8" />
        </td>
        <td id="ele27" class="eleTD">
          <Element {langValue} name={Lang[Constants[26].nme]} constants={Constants[26]} className="transitionMetals r4 c9" />
        </td>
        <td id="ele28" class="eleTD">
          <Element {langValue} name={Lang[Constants[27].nme]} constants={Constants[27]} className="transitionMetals r4 c10" />
        </td>
        <td id="ele29" class="eleTD">
          <Element {langValue} name={Lang[Constants[28].nme]} constants={Constants[28]} className="transitionMetals r4 c11" />
        </td>
        <td id="ele30" class="eleTD">
          <Element {langValue} name={Lang[Constants[29].nme]} constants={Constants[29]} className="transitionMetals r4 c12" />
        </td>
        <td id="ele31" class="eleTD">
          <Element {langValue} name={Lang[Constants[30].nme]} constants={Constants[30]} className="postTransitionMetals r4 c13" />
        </td>
        <td id="ele32" class="eleTD">
          <Element {langValue} name={Lang[Constants[31].nme]} constants={Constants[31]} className="metalloids r4 c14" />
        </td>
        <td id="ele33" class="eleTD">
          <Element {langValue} name={Lang[Constants[32].nme]} constants={Constants[32]} className="metalloids r4 c15" />
        </td>
        <td id="ele34" class="eleTD">
          <Element {langValue} name={Lang[Constants[33].nme]} constants={Constants[33]} className="otherNonmetals r4 c16" />
        </td>
        <td id="ele35" class="eleTD">
          <Element {langValue} name={Lang[Constants[34].nme]} constants={Constants[34]} className="halogens r4 c17" />
        </td>
        <td id="ele36" class="eleTD">
          <Element {langValue} name={Lang[Constants[35].nme]} constants={Constants[35]} className="nobleGases r4 c18" />
        </td>
      </tr>
      <tr>
        <td id="period5" class="periods unselectable r5 text-center">5</td>
        <td id="ele37" class="eleTD">
          <Element {langValue} name={Lang[Constants[36].nme]} constants={Constants[36]} className="alkaliMetals r5 c1" />
        </td>
        <td id="ele38" class="eleTD">
          <Element {langValue} name={Lang[Constants[37].nme]} constants={Constants[37]} className="alkalineEarthMetals r5 c2" />
        </td>
        <td id="ele39" class="eleTD">
          <Element {langValue} name={Lang[Constants[38].nme]} constants={Constants[38]} className="transitionMetals r5 c3" />
        </td>
        <td id="ele40" class="eleTD">
          <Element {langValue} name={Lang[Constants[39].nme]} constants={Constants[39]} className="transitionMetals r5 c4" />
        </td>
        <td id="ele41" class="eleTD">
          <Element {langValue} name={Lang[Constants[40].nme]} constants={Constants[40]} className="transitionMetals r5 c5" />
        </td>
        <td id="ele42" class="eleTD">
          <Element {langValue} name={Lang[Constants[41].nme]} constants={Constants[41]} className="transitionMetals r5 c6" />
        </td>
        <td id="ele43" class="eleTD">
          <Element {langValue} name={Lang[Constants[42].nme]} constants={Constants[42]} className="transitionMetals r5 c7" />
        </td>
        <td id="ele44" class="eleTD">
          <Element {langValue} name={Lang[Constants[43].nme]} constants={Constants[43]} className="transitionMetals r5 c8" />
        </td>
        <td id="ele45" class="eleTD">
          <Element {langValue} name={Lang[Constants[44].nme]} constants={Constants[44]} className="transitionMetals r5 c9" />
        </td>
        <td id="ele46" class="eleTD">
          <Element {langValue} name={Lang[Constants[45].nme]} constants={Constants[45]} className="transitionMetals r5 c10" />
        </td>
        <td id="ele47" class="eleTD">
          <Element {langValue} name={Lang[Constants[46].nme]} constants={Constants[46]} className="transitionMetals r5 c11" />
        </td>
        <td id="ele48" class="eleTD">
          <Element {langValue} name={Lang[Constants[47].nme]} constants={Constants[47]} className="transitionMetals r5 c12" />
        </td>
        <td id="ele49" class="eleTD">
          <Element {langValue} name={Lang[Constants[48].nme]} constants={Constants[48]} className="postTransitionMetals r5 c13" />
        </td>
        <td id="ele50" class="eleTD">
          <Element {langValue} name={Lang[Constants[49].nme]} constants={Constants[49]} className="postTransitionMetals r5 c14" />
        </td>
        <td id="ele51" class="eleTD">
          <Element {langValue} name={Lang[Constants[50].nme]} constants={Constants[50]} className="metalloids r5 c15" />
        </td>
        <td id="ele52" class="eleTD">
          <Element {langValue} name={Lang[Constants[51].nme]} constants={Constants[51]} className="metalloids r5 c16" />
        </td>
        <td id="ele53" class="eleTD">
          <Element {langValue} name={Lang[Constants[52].nme]} constants={Constants[52]} className="halogens r5 c17" />
        </td>
        <td id="ele54" class="eleTD">
          <Element {langValue} name={Lang[Constants[53].nme]} constants={Constants[53]} className="nobleGases r5 c18" />
        </td>
      </tr>
      <tr>
        <td id="period6" class="periods unselectable r6 text-center">6</td>
        <td id="ele55" class="eleTD">
          <Element {langValue} name={Lang[Constants[54].nme]} constants={Constants[54]} className="alkaliMetals r6 c1" />
        </td>
        <td id="ele56" class="eleTD">
          <Element {langValue} name={Lang[Constants[55].nme]} constants={Constants[55]} className="alkalineEarthMetals r6 c2" />
        </td>
        <td id="star1" class="text-center">*</td>
        <td id="ele72" class="eleTD">
          <Element {langValue} name={Lang[Constants[71].nme]} constants={Constants[71]} className="transitionMetals r6 c4" />
        </td>
        <td id="ele73" class="eleTD">
          <Element {langValue} name={Lang[Constants[72].nme]} constants={Constants[72]} className="transitionMetals r6 c5" />
        </td>
        <td id="ele74" class="eleTD">
          <Element {langValue} name={Lang[Constants[73].nme]} constants={Constants[73]} className="transitionMetals r6 c6" />
        </td>
        <td id="ele75" class="eleTD">
          <Element {langValue} name={Lang[Constants[74].nme]} constants={Constants[74]} className="transitionMetals r6 c7" />
        </td>
        <td id="ele76" class="eleTD">
          <Element {langValue} name={Lang[Constants[75].nme]} constants={Constants[75]} className="transitionMetals r6 c8" />
        </td>
        <td id="ele77" class="eleTD">
          <Element {langValue} name={Lang[Constants[76].nme]} constants={Constants[76]} className="transitionMetals r6 c9" />
        </td>
        <td id="ele78" class="eleTD">
          <Element {langValue} name={Lang[Constants[77].nme]} constants={Constants[77]} className="transitionMetals r6 c10" />
        </td>
        <td id="ele79" class="eleTD">
          <Element {langValue} name={Lang[Constants[78].nme]} constants={Constants[78]} className="transitionMetals r6 c11" />
        </td>
        <td id="ele80" class="eleTD">
          <Element {langValue} name={Lang[Constants[79].nme]} constants={Constants[79]} className="transitionMetals r6 c12" />
        </td>
        <td id="ele81" class="eleTD">
          <Element {langValue} name={Lang[Constants[80].nme]} constants={Constants[80]} className="postTransitionMetals r6 c13" />
        </td>
        <td id="ele82" class="eleTD">
          <Element {langValue} name={Lang[Constants[81].nme]} constants={Constants[81]} className="postTransitionMetals r6 c14" />
        </td>
        <td id="ele83" class="eleTD">
          <Element {langValue} name={Lang[Constants[82].nme]} constants={Constants[82]} className="postTransitionMetals r6 c15" />
        </td>
        <td id="ele84" class="eleTD">
          <Element {langValue} name={Lang[Constants[83].nme]} constants={Constants[83]} className="metalloids r6 c16" />
        </td>
        <td id="ele85" class="eleTD">
          <Element {langValue} name={Lang[Constants[84].nme]} constants={Constants[84]} className="halogens r6 c17" />
        </td>
        <td id="ele86" class="eleTD">
          <Element {langValue} name={Lang[Constants[85].nme]} constants={Constants[85]} className="nobleGases r6 c18" />
        </td>
      </tr>
      <tr>
        <td id="period7" class="periods unselectable r7 text-center">7</td>
        <td id="ele87" class="eleTD">
          <Element {langValue} name={Lang[Constants[86].nme]} constants={Constants[86]} className="alkaliMetals r7 c1" />
        </td>
        <td id="ele88" class="eleTD">
          <Element {langValue} name={Lang[Constants[87].nme]} constants={Constants[87]} className="alkalineEarthMetals r7 c2" />
        </td>
        <td id="star2" class="text-center">**</td>
        <td id="ele104" class="eleTD">
          <Element {langValue} name={Lang[Constants[103].nme]} constants={Constants[103]} className="transitionMetals r7 c4" />
        </td>
        <td id="ele105" class="eleTD">
          <Element {langValue} name={Lang[Constants[104].nme]} constants={Constants[104]} className="transitionMetals r7 c5" />
        </td>
        <td id="ele106" class="eleTD">
          <Element {langValue} name={Lang[Constants[105].nme]} constants={Constants[105]} className="transitionMetals r7 c6" />
        </td>
        <td id="ele107" class="eleTD">
          <Element {langValue} name={Lang[Constants[106].nme]} constants={Constants[106]} className="transitionMetals r7 c7" />
        </td>
        <td id="ele108" class="eleTD">
          <Element {langValue} name={Lang[Constants[107].nme]} constants={Constants[107]} className="transitionMetals r7 c8" />
        </td>
        <td id="ele109" class="eleTD">
          <Element {langValue} name={Lang[Constants[108].nme]} constants={Constants[108]} className="transitionMetals r7 c9" />
        </td>
        <td id="ele110" class="eleTD">
          <Element {langValue} name={Lang[Constants[109].nme]} constants={Constants[109]} className="transitionMetals r7 c10" />
        </td>
        <td id="ele111" class="eleTD">
          <Element {langValue} name={Lang[Constants[110].nme]} constants={Constants[110]} className="transitionMetals r7 c11" />
        </td>
        <td id="ele112" class="eleTD">
          <Element {langValue} name={Lang[Constants[111].nme]} constants={Constants[111]} className="transitionMetals r7 c12" />
        </td>
        <td id="ele113" class="eleTD">
          <Element {langValue} name={Lang[Constants[112].nme]} constants={Constants[112]} className="postTransitionMetals r7 c13" />
        </td>
        <td id="ele114" class="eleTD">
          <Element {langValue} name={Lang[Constants[113].nme]} constants={Constants[113]} className="postTransitionMetals r7 c14" />
        </td>
        <td id="ele115" class="eleTD">
          <Element {langValue} name={Lang[Constants[114].nme]} constants={Constants[114]} className="postTransitionMetals r7 c15" />
        </td>
        <td id="ele116" class="eleTD">
          <Element {langValue} name={Lang[Constants[115].nme]} constants={Constants[115]} className="postTransitionMetals r7 c16" />
        </td>
        <td id="ele117" class="eleTD">
          <Element {langValue} name={Lang[Constants[116].nme]} constants={Constants[116]} className="halogens r7 c17" />
        </td>
        <td id="ele118" class="eleTD">
          <Element {langValue} name={Lang[Constants[116].nme]} constants={Constants[116]} className="nobleGases r7 c18" />
        </td>
      </tr>
      <tr>
        <td class="gap" />
      </tr>
      <tr>
        <td />
        <td colspan="2" id="lanthanides" class="text-left"><span>* </span><span id="lanthanidesMain" /></td>
        <td id="ele57" class="eleTD">
          <Element {langValue} name={Lang[Constants[56].nme]} constants={Constants[56]} className="lanthanides r6" />
        </td>
        <td id="ele58" class="eleTD">
          <Element {langValue} name={Lang[Constants[57].nme]} constants={Constants[57]} className="lanthanides r6" />
        </td>
        <td id="ele59" class="eleTD">
          <Element {langValue} name={Lang[Constants[58].nme]} constants={Constants[58]} className="lanthanides r6" />
        </td>
        <td id="ele60" class="eleTD">
          <Element {langValue} name={Lang[Constants[59].nme]} constants={Constants[59]} className="lanthanides r6" />
        </td>
        <td id="ele61" class="eleTD">
          <Element {langValue} name={Lang[Constants[60].nme]} constants={Constants[60]} className="lanthanides r6" />
        </td>
        <td id="ele62" class="eleTD">
          <Element {langValue} name={Lang[Constants[61].nme]} constants={Constants[61]} className="lanthanides r6" />
        </td>
        <td id="ele63" class="eleTD">
          <Element {langValue} name={Lang[Constants[62].nme]} constants={Constants[62]} className="lanthanides r6" />
        </td>
        <td id="ele64" class="eleTD">
          <Element {langValue} name={Lang[Constants[63].nme]} constants={Constants[63]} className="lanthanides r6" />
        </td>
        <td id="ele65" class="eleTD">
          <Element {langValue} name={Lang[Constants[64].nme]} constants={Constants[64]} className="lanthanides r6" />
        </td>
        <td id="ele66" class="eleTD">
          <Element {langValue} name={Lang[Constants[65].nme]} constants={Constants[65]} className="lanthanides r6" />
        </td>
        <td id="ele67" class="eleTD">
          <Element {langValue} name={Lang[Constants[66].nme]} constants={Constants[66]} className="lanthanides r6" />
        </td>
        <td id="ele68" class="eleTD">
          <Element {langValue} name={Lang[Constants[67].nme]} constants={Constants[67]} className="lanthanides r6" />
        </td>
        <td id="ele69" class="eleTD">
          <Element {langValue} name={Lang[Constants[68].nme]} constants={Constants[68]} className="lanthanides r6" />
        </td>
        <td id="ele70" class="eleTD">
          <Element {langValue} name={Lang[Constants[69].nme]} constants={Constants[69]} className="lanthanides r6" />
        </td>
        <td id="ele71" class="eleTD">
          <Element {langValue} name={Lang[Constants[70].nme]} constants={Constants[70]} className="lanthanides r6" />
        </td>
      </tr>
      <tr>
        <td />
        <td colspan="2" id="actinides" class="text-left"><span>** </span><span id="actinidesMain" /></td>
        <td id="ele89" class="eleTD">
          <Element {langValue} name={Lang[Constants[88].nme]} constants={Constants[88]} className="actinides r7" />
        </td>
        <td id="ele90" class="eleTD">
          <Element {langValue} name={Lang[Constants[89].nme]} constants={Constants[89]} className="actinides r7" />
        </td>
        <td id="ele91" class="eleTD">
          <Element {langValue} name={Lang[Constants[90].nme]} constants={Constants[90]} className="actinides r7" />
        </td>
        <td id="ele92" class="eleTD">
          <Element {langValue} name={Lang[Constants[91].nme]} constants={Constants[91]} className="actinides r7" />
        </td>
        <td id="ele93" class="eleTD">
          <Element {langValue} name={Lang[Constants[92].nme]} constants={Constants[92]} className="actinides r7" />
        </td>
        <td id="ele94" class="eleTD">
          <Element {langValue} name={Lang[Constants[93].nme]} constants={Constants[93]} className="actinides r7" />
        </td>
        <td id="ele95" class="eleTD">
          <Element {langValue} name={Lang[Constants[94].nme]} constants={Constants[94]} className="actinides r7" />
        </td>
        <td id="ele96" class="eleTD">
          <Element {langValue} name={Lang[Constants[95].nme]} constants={Constants[95]} className="actinides r7" />
        </td>
        <td id="ele97" class="eleTD">
          <Element {langValue} name={Lang[Constants[96].nme]} constants={Constants[96]} className="actinides r7" />
        </td>
        <td id="ele98" class="eleTD">
          <Element {langValue} name={Lang[Constants[97].nme]} constants={Constants[97]} className="actinides r7" />
        </td>
        <td id="ele99" class="eleTD">
          <Element {langValue} name={Lang[Constants[98].nme]} constants={Constants[98]} className="actinides r7" />
        </td>
        <td id="ele100" class="eleTD">
          <Element {langValue} name={Lang[Constants[99].nme]} constants={Constants[99]} className="actinides r7" />
        </td>
        <td id="ele101" class="eleTD">
          <Element {langValue} name={Lang[Constants[100].nme]} constants={Constants[100]} className="actinides r7" />
        </td>
        <td id="ele102" class="eleTD">
          <Element {langValue} name={Lang[Constants[101].nme]} constants={Constants[101]} className="actinides r7" />
        </td>
        <td id="ele103" class="eleTD">
          <Element {langValue} name={Lang[Constants[102].nme]} constants={Constants[102]} className="actinides r7" />
        </td>
      </tr>
      <tr>
        <td class="gap" />
      </tr>
      <tr>
        <td />
        <td colspan="18">
          <div class="flex text-center margin-bottom-20 width-100">
            <div class="flex-auto category alkaliMetals unselectable">{Lang.cat1}</div>
            <div class="flex-auto category alkalineEarthMetals unselectable">{Lang.cat2}</div>
            <div class="flex-auto category transitionMetals unselectable">{Lang.cat3}</div>
            <div class="flex-auto category postTransitionMetals unselectable">{Lang.cat4}</div>
            <div class="flex-auto category otherNonmetals unselectable">{Lang.cat5}</div>
            <div class="flex-auto category metalloids unselectable">{Lang.cat6}</div>
            <div class="flex-auto category halogens unselectable">{Lang.cat7}</div>
            <div class="flex-auto category nobleGases unselectable">{Lang.cat8}</div>
            <div class="flex-auto category lanthanides unselectable">{Lang.lanthanides}</div>
            <div class="flex-auto category actinides unselectable">{Lang.actinides}</div>
          </div>
        </td>
      </tr>
      <tr />
    </tbody>
  </table>
</div>
