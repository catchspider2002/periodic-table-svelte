<script context="module">
  export function preload() {
    return this.fetch(`fr.json`)
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
          <a href="element.html?num=4" id="element4" class="elements alkalineEarthMetals r2 c2">
            <div class="eleNum">4</div>
            <div class="eleSym heavyFont">Be</div>
            <div class="eleNm" id="beryllium" />
            <div class="eleWt">9.012182</div>
          </a>
        </td>
        <td id="ele5" class="eleTD">
          <a href="element.html?num=5" id="element5" class="elements metalloids r2 c13">
            <div class="eleNum">5</div>
            <div class="eleSym heavyFont">B</div>
            <div class="eleNm" id="boron" />
            <div class="eleWt">10.811</div>
          </a>
        </td>
        <td id="ele6" class="eleTD">
          <a href="element.html?num=6" id="element6" class="elements otherNonmetals r2 c14">
            <div class="eleNum">6</div>
            <div class="eleSym heavyFont">C</div>
            <div class="eleNm" id="carbon" />
            <div class="eleWt">12.0107</div>
          </a>
        </td>
        <td id="ele7" class="eleTD">
          <a href="element.html?num=7" id="element7" class="elements otherNonmetals r2 c15">
            <div class="eleNum">7</div>
            <div class="eleSym heavyFont">N</div>
            <div class="eleNm" id="nitrogen" />
            <div class="eleWt">14.0067</div>
          </a>
        </td>
        <td id="ele8" class="eleTD">
          <a href="element.html?num=8" id="element8" class="elements otherNonmetals r2 c16">
            <div class="eleNum">8</div>
            <div class="eleSym heavyFont">O</div>
            <div class="eleNm" id="oxygen" />
            <div class="eleWt">15.9994</div>
          </a>
        </td>
        <td id="ele9" class="eleTD">
          <a href="element.html?num=9" id="element9" class="elements halogens r2 c17">
            <div class="eleNum">9</div>
            <div class="eleSym heavyFont">F</div>
            <div class="eleNm" id="fluorine" />
            <div class="eleWt">18.9984032</div>
          </a>
        </td>
        <td id="ele10" class="eleTD">
          <a href="element.html?num=10" id="element10" class="elements nobleGases r2 c18">
            <div class="eleNum">10</div>
            <div class="eleSym heavyFont">Ne</div>
            <div class="eleNm" id="neon" />
            <div class="eleWt">20.1797</div>
          </a>
        </td>
      </tr>
      <tr>
        <td id="period3" class="periods unselectable r3 text-center">3</td>
        <td id="ele11" class="eleTD">
          <a href="element.html?num=11" id="element11" class="elements alkaliMetals r3 c1">
            <div class="eleNum">11</div>
            <div class="eleSym heavyFont">Na</div>
            <div class="eleNm" id="sodium" />
            <div class="eleWt">22.98976928</div>
          </a>
        </td>
        <td id="ele12" class="eleTD">
          <a href="element.html?num=12" id="element12" class="elements alkalineEarthMetals r3 c2">
            <div class="eleNum">12</div>
            <div class="eleSym heavyFont">Mg</div>
            <div class="eleNm" id="magnesium" />
            <div class="eleWt">24.305</div>
          </a>
        </td>
        <td id="ele13" class="eleTD">
          <a href="element.html?num=13" id="element13" class="elements postTransitionMetals r3 c13">
            <div class="eleNum">13</div>
            <div class="eleSym heavyFont">Al</div>
            <div class="eleNm" id="aluminium" />
            <div class="eleWt">26.9815386</div>
          </a>
        </td>
        <td id="ele14" class="eleTD">
          <a href="element.html?num=14" id="element14" class="elements metalloids r3 c14">
            <div class="eleNum">14</div>
            <div class="eleSym heavyFont">Si</div>
            <div class="eleNm" id="silicon" />
            <div class="eleWt">28.0855</div>
          </a>
        </td>
        <td id="ele15" class="eleTD">
          <a href="element.html?num=15" id="element15" class="elements otherNonmetals r3 c15">
            <div class="eleNum">15</div>
            <div class="eleSym heavyFont">P</div>
            <div class="eleNm" id="phosphorus" />
            <div class="eleWt">30.973762</div>
          </a>
        </td>
        <td id="ele16" class="eleTD">
          <a href="element.html?num=16" id="element16" class="elements otherNonmetals r3 c16">
            <div class="eleNum">16</div>
            <div class="eleSym heavyFont">S</div>
            <div class="eleNm" id="sulfur" />
            <div class="eleWt">32.065</div>
          </a>
        </td>
        <td id="ele17" class="eleTD">
          <a href="element.html?num=17" id="element17" class="elements halogens r3 c17">
            <div class="eleNum">17</div>
            <div class="eleSym heavyFont">Cl</div>
            <div class="eleNm" id="chlorine" />
            <div class="eleWt">35.453</div>
          </a>
        </td>
        <td id="ele18" class="eleTD">
          <a href="element.html?num=18" id="element18" class="elements nobleGases r3 c18">
            <div class="eleNum">18</div>
            <div class="eleSym heavyFont">Ar</div>
            <div class="eleNm" id="argon" />
            <div class="eleWt">39.948</div>
          </a>
        </td>
      </tr>
      <tr>
        <td id="period4" class="periods unselectable r4 text-center">4</td>
        <td id="ele19" class="eleTD">
          <a href="element.html?num=19" id="element19" class="elements alkaliMetals r4 c1">
            <div class="eleNum">19</div>
            <div class="eleSym heavyFont">K</div>
            <div class="eleNm" id="potassium" />
            <div class="eleWt">39.0983</div>
          </a>
        </td>
        <td id="ele20" class="eleTD">
          <a href="element.html?num=20" id="element20" class="elements alkalineEarthMetals r4 c2">
            <div class="eleNum">20</div>
            <div class="eleSym heavyFont">Ca</div>
            <div class="eleNm" id="calcium" />
            <div class="eleWt">40.078</div>
          </a>
        </td>
        <td id="ele21" class="eleTD">
          <a href="element.html?num=21" id="element21" class="elements transitionMetals r4 c3">
            <div class="eleNum">21</div>
            <div class="eleSym heavyFont">Sc</div>
            <div class="eleNm" id="scandium" />
            <div class="eleWt">44.955912</div>
          </a>
        </td>
        <td id="ele22" class="eleTD">
          <a href="element.html?num=22" id="element22" class="elements transitionMetals r4 c4">
            <div class="eleNum">22</div>
            <div class="eleSym heavyFont">Ti</div>
            <div class="eleNm" id="titanium" />
            <div class="eleWt">47.867</div>
          </a>
        </td>
        <td id="ele23" class="eleTD">
          <a href="element.html?num=23" id="element23" class="elements transitionMetals r4 c5">
            <div class="eleNum">23</div>
            <div class="eleSym heavyFont">V</div>
            <div class="eleNm" id="vanadium" />
            <div class="eleWt">50.9415</div>
          </a>
        </td>
        <td id="ele24" class="eleTD">
          <a href="element.html?num=24" id="element24" class="elements transitionMetals r4 c6">
            <div class="eleNum">24</div>
            <div class="eleSym heavyFont">Cr</div>
            <div class="eleNm" id="chromium" />
            <div class="eleWt">51.9961</div>
          </a>
        </td>
        <td id="ele25" class="eleTD">
          <a href="element.html?num=25" id="element25" class="elements transitionMetals r4 c7">
            <div class="eleNum">25</div>
            <div class="eleSym heavyFont">Mn</div>
            <div class="eleNm" id="manganese" />
            <div class="eleWt">54.938045</div>
          </a>
        </td>
        <td id="ele26" class="eleTD">
          <a href="element.html?num=26" id="element26" class="elements transitionMetals r4 c8">
            <div class="eleNum">26</div>
            <div class="eleSym heavyFont">Fe</div>
            <div class="eleNm" id="iron" />
            <div class="eleWt">55.845</div>
          </a>
        </td>
        <td id="ele27" class="eleTD">
          <a href="element.html?num=27" id="element27" class="elements transitionMetals r4 c9">
            <div class="eleNum">27</div>
            <div class="eleSym heavyFont">Co</div>
            <div class="eleNm" id="cobalt" />
            <div class="eleWt">58.933195</div>
          </a>
        </td>
        <td id="ele28" class="eleTD">
          <a href="element.html?num=28" id="element28" class="elements transitionMetals r4 c10">
            <div class="eleNum">28</div>
            <div class="eleSym heavyFont">Ni</div>
            <div class="eleNm" id="nickel" />
            <div class="eleWt">58.6934</div>
          </a>
        </td>
        <td id="ele29" class="eleTD">
          <a href="element.html?num=29" id="element29" class="elements transitionMetals r4 c11">
            <div class="eleNum">29</div>
            <div class="eleSym heavyFont">Cu</div>
            <div class="eleNm" id="copper" />
            <div class="eleWt">63.546</div>
          </a>
        </td>
        <td id="ele30" class="eleTD">
          <a href="element.html?num=30" id="element30" class="elements transitionMetals r4 c12">
            <div class="eleNum">30</div>
            <div class="eleSym heavyFont">Zn</div>
            <div class="eleNm" id="zinc" />
            <div class="eleWt">65.38</div>
          </a>
        </td>
        <td id="ele31" class="eleTD">
          <a href="element.html?num=31" id="element31" class="elements postTransitionMetals r4 c13">
            <div class="eleNum">31</div>
            <div class="eleSym heavyFont">Ga</div>
            <div class="eleNm" id="gallium" />
            <div class="eleWt">69.723</div>
          </a>
        </td>
        <td id="ele32" class="eleTD">
          <a href="element.html?num=32" id="element32" class="elements metalloids r4 c14">
            <div class="eleNum">32</div>
            <div class="eleSym heavyFont">Ge</div>
            <div class="eleNm" id="germanium" />
            <div class="eleWt">72.63</div>
          </a>
        </td>
        <td id="ele33" class="eleTD">
          <a href="element.html?num=33" id="element33" class="elements metalloids r4 c15">
            <div class="eleNum">33</div>
            <div class="eleSym heavyFont">As</div>
            <div class="eleNm" id="arsenic" />
            <div class="eleWt">74.9216</div>
          </a>
        </td>
        <td id="ele34" class="eleTD">
          <a href="element.html?num=34" id="element34" class="elements otherNonmetals r4 c16">
            <div class="eleNum">34</div>
            <div class="eleSym heavyFont">Se</div>
            <div class="eleNm" id="selenium" />
            <div class="eleWt">78.96</div>
          </a>
        </td>
        <td id="ele35" class="eleTD">
          <a href="element.html?num=35" id="element35" class="elements halogens r4 c17">
            <div class="eleNum">35</div>
            <div class="eleSym heavyFont">Br</div>
            <div class="eleNm" id="bromine" />
            <div class="eleWt">79.904</div>
          </a>
        </td>
        <td id="ele36" class="eleTD">
          <a href="element.html?num=36" id="element36" class="elements nobleGases r4 c18">
            <div class="eleNum">36</div>
            <div class="eleSym heavyFont">Kr</div>
            <div class="eleNm" id="krypton" />
            <div class="eleWt">83.798</div>
          </a>
        </td>
      </tr>
      <tr>
        <td id="period5" class="periods unselectable r5 text-center">5</td>
        <td id="ele37" class="eleTD">
          <a href="element.html?num=37" id="element37" class="elements alkaliMetals r5 c1">
            <div class="eleNum">37</div>
            <div class="eleSym heavyFont">Rb</div>
            <div class="eleNm" id="rubidium" />
            <div class="eleWt">85.4678</div>
          </a>
        </td>
        <td id="ele38" class="eleTD">
          <a href="element.html?num=38" id="element38" class="elements alkalineEarthMetals r5 c2">
            <div class="eleNum">38</div>
            <div class="eleSym heavyFont">Sr</div>
            <div class="eleNm" id="strontium" />
            <div class="eleWt">87.62</div>
          </a>
        </td>
        <td id="ele39" class="eleTD">
          <a href="element.html?num=39" id="element39" class="elements transitionMetals r5 c3">
            <div class="eleNum">39</div>
            <div class="eleSym heavyFont">Y</div>
            <div class="eleNm" id="yttrium" />
            <div class="eleWt">88.90585</div>
          </a>
        </td>
        <td id="ele40" class="eleTD">
          <a href="element.html?num=40" id="element40" class="elements transitionMetals r5 c4">
            <div class="eleNum">40</div>
            <div class="eleSym heavyFont">Zr</div>
            <div class="eleNm" id="zirconium" />
            <div class="eleWt">91.224</div>
          </a>
        </td>
        <td id="ele41" class="eleTD">
          <a href="element.html?num=41" id="element41" class="elements transitionMetals r5 c5">
            <div class="eleNum">41</div>
            <div class="eleSym heavyFont">Nb</div>
            <div class="eleNm" id="niobium" />
            <div class="eleWt">92.90638</div>
          </a>
        </td>
        <td id="ele42" class="eleTD">
          <a href="element.html?num=42" id="element42" class="elements transitionMetals r5 c6">
            <div class="eleNum">42</div>
            <div class="eleSym heavyFont">Mo</div>
            <div class="eleNm" id="molybdenum" />
            <div class="eleWt">95.96</div>
          </a>
        </td>
        <td id="ele43" class="eleTD">
          <a href="element.html?num=43" id="element43" class="elements transitionMetals r5 c7">
            <div class="eleNum">43</div>
            <div class="eleSym heavyFont">Tc</div>
            <div class="eleNm" id="technetium" />
            <div class="eleWt">[98]</div>
          </a>
        </td>
        <td id="ele44" class="eleTD">
          <a href="element.html?num=44" id="element44" class="elements transitionMetals r5 c8">
            <div class="eleNum">44</div>
            <div class="eleSym heavyFont">Ru</div>
            <div class="eleNm" id="ruthenium" />
            <div class="eleWt">101.07</div>
          </a>
        </td>
        <td id="ele45" class="eleTD">
          <a href="element.html?num=45" id="element45" class="elements transitionMetals r5 c9">
            <div class="eleNum">45</div>
            <div class="eleSym heavyFont">Rh</div>
            <div class="eleNm" id="rhodium" />
            <div class="eleWt">102.9055</div>
          </a>
        </td>
        <td id="ele46" class="eleTD">
          <a href="element.html?num=46" id="element46" class="elements transitionMetals r5 c10">
            <div class="eleNum">46</div>
            <div class="eleSym heavyFont">Pd</div>
            <div class="eleNm" id="palladium" />
            <div class="eleWt">106.42</div>
          </a>
        </td>
        <td id="ele47" class="eleTD">
          <a href="element.html?num=47" id="element47" class="elements transitionMetals r5 c11">
            <div class="eleNum">47</div>
            <div class="eleSym heavyFont">Ag</div>
            <div class="eleNm" id="silver" />
            <div class="eleWt">107.8682</div>
          </a>
        </td>
        <td id="ele48" class="eleTD">
          <a href="element.html?num=48" id="element48" class="elements transitionMetals r5 c12">
            <div class="eleNum">48</div>
            <div class="eleSym heavyFont">Cd</div>
            <div class="eleNm" id="cadmium" />
            <div class="eleWt">112.411</div>
          </a>
        </td>
        <td id="ele49" class="eleTD">
          <a href="element.html?num=49" id="element49" class="elements postTransitionMetals r5 c13">
            <div class="eleNum">49</div>
            <div class="eleSym heavyFont">In</div>
            <div class="eleNm" id="indium" />
            <div class="eleWt">114.818</div>
          </a>
        </td>
        <td id="ele50" class="eleTD">
          <a href="element.html?num=50" id="element50" class="elements postTransitionMetals r5 c14">
            <div class="eleNum">50</div>
            <div class="eleSym heavyFont">Sn</div>
            <div class="eleNm" id="tin" />
            <div class="eleWt">118.71</div>
          </a>
        </td>
        <td id="ele51" class="eleTD">
          <a href="element.html?num=51" id="element51" class="elements metalloids r5 c15">
            <div class="eleNum">51</div>
            <div class="eleSym heavyFont">Sb</div>
            <div class="eleNm" id="antimony" />
            <div class="eleWt">121.76</div>
          </a>
        </td>
        <td id="ele52" class="eleTD">
          <a href="element.html?num=52" id="element52" class="elements metalloids r5 c16">
            <div class="eleNum">52</div>
            <div class="eleSym heavyFont">Te</div>
            <div class="eleNm" id="tellurium" />
            <div class="eleWt">127.6</div>
          </a>
        </td>
        <td id="ele53" class="eleTD">
          <a href="element.html?num=53" id="element53" class="elements halogens r5 c17">
            <div class="eleNum">53</div>
            <div class="eleSym heavyFont">I</div>
            <div class="eleNm" id="iodine" />
            <div class="eleWt">126.90447</div>
          </a>
        </td>
        <td id="ele54" class="eleTD">
          <a href="element.html?num=54" id="element54" class="elements nobleGases r5 c18">
            <div class="eleNum">54</div>
            <div class="eleSym heavyFont">Xe</div>
            <div class="eleNm" id="xenon" />
            <div class="eleWt">131.293</div>
          </a>
        </td>
      </tr>
      <tr>
        <td id="period6" class="periods unselectable r6 text-center">6</td>
        <td id="ele55" class="eleTD">
          <a href="element.html?num=55" id="element55" class="elements alkaliMetals r6 c1">
            <div class="eleNum">55</div>
            <div class="eleSym heavyFont">Cs</div>
            <div class="eleNm" id="caesium" />
            <div class="eleWt">132.9054519</div>
          </a>
        </td>
        <td id="ele56" class="eleTD">
          <a href="element.html?num=56" id="element56" class="elements alkalineEarthMetals r6 c2">
            <div class="eleNum">56</div>
            <div class="eleSym heavyFont">Ba</div>
            <div class="eleNm" id="barium" />
            <div class="eleWt">137.327</div>
          </a>
        </td>
        <td id="star1" class="text-center">*</td>
        <td id="ele72" class="eleTD">
          <a href="element.html?num=72" id="element72" class="elements transitionMetals r6 c4">
            <div class="eleNum">72</div>
            <div class="eleSym heavyFont">Hf</div>
            <div class="eleNm" id="hafnium" />
            <div class="eleWt">178.49</div>
          </a>
        </td>
        <td id="ele73" class="eleTD">
          <a href="element.html?num=73" id="element73" class="elements transitionMetals r6 c5">
            <div class="eleNum">73</div>
            <div class="eleSym heavyFont">Ta</div>
            <div class="eleNm" id="tantalum" />
            <div class="eleWt">180.94788</div>
          </a>
        </td>
        <td id="ele74" class="eleTD">
          <a href="element.html?num=74" id="element74" class="elements transitionMetals r6 c6">
            <div class="eleNum">74</div>
            <div class="eleSym heavyFont">W</div>
            <div class="eleNm" id="tungsten" />
            <div class="eleWt">183.84</div>
          </a>
        </td>
        <td id="ele75" class="eleTD">
          <a href="element.html?num=75" id="element75" class="elements transitionMetals r6 c7">
            <div class="eleNum">75</div>
            <div class="eleSym heavyFont">Re</div>
            <div class="eleNm" id="rhenium" />
            <div class="eleWt">186.207</div>
          </a>
        </td>
        <td id="ele76" class="eleTD">
          <a href="element.html?num=76" id="element76" class="elements transitionMetals r6 c8">
            <div class="eleNum">76</div>
            <div class="eleSym heavyFont">Os</div>
            <div class="eleNm" id="osmium" />
            <div class="eleWt">190.23</div>
          </a>
        </td>
        <td id="ele77" class="eleTD">
          <a href="element.html?num=77" id="element77" class="elements transitionMetals r6 c9">
            <div class="eleNum">77</div>
            <div class="eleSym heavyFont">Ir</div>
            <div class="eleNm" id="iridium" />
            <div class="eleWt">192.217</div>
          </a>
        </td>
        <td id="ele78" class="eleTD">
          <a href="element.html?num=78" id="element78" class="elements transitionMetals r6 c10">
            <div class="eleNum">78</div>
            <div class="eleSym heavyFont">Pt</div>
            <div class="eleNm" id="platinum" />
            <div class="eleWt">195.084</div>
          </a>
        </td>
        <td id="ele79" class="eleTD">
          <a href="element.html?num=79" id="element79" class="elements transitionMetals r6 c11">
            <div class="eleNum">79</div>
            <div class="eleSym heavyFont">Au</div>
            <div class="eleNm" id="gold" />
            <div class="eleWt">196.966569</div>
          </a>
        </td>
        <td id="ele80" class="eleTD">
          <a href="element.html?num=80" id="element80" class="elements transitionMetals r6 c12">
            <div class="eleNum">80</div>
            <div class="eleSym heavyFont">Hg</div>
            <div class="eleNm" id="mercury" />
            <div class="eleWt">200.59</div>
          </a>
        </td>
        <td id="ele81" class="eleTD">
          <a href="element.html?num=81" id="element81" class="elements postTransitionMetals r6 c13">
            <div class="eleNum">81</div>
            <div class="eleSym heavyFont">Tl</div>
            <div class="eleNm" id="thallium" />
            <div class="eleWt">204.3833</div>
          </a>
        </td>
        <td id="ele82" class="eleTD">
          <a href="element.html?num=82" id="element82" class="elements postTransitionMetals r6 c14">
            <div class="eleNum">82</div>
            <div class="eleSym heavyFont">Pb</div>
            <div class="eleNm" id="lead" />
            <div class="eleWt">207.2</div>
          </a>
        </td>
        <td id="ele83" class="eleTD">
          <a href="element.html?num=83" id="element83" class="elements postTransitionMetals r6 c15">
            <div class="eleNum">83</div>
            <div class="eleSym heavyFont">Bi</div>
            <div class="eleNm" id="bismuth" />
            <div class="eleWt">208.9804</div>
          </a>
        </td>
        <td id="ele84" class="eleTD">
          <a href="element.html?num=84" id="element84" class="elements metalloids r6 c16">
            <div class="eleNum">84</div>
            <div class="eleSym heavyFont">Po</div>
            <div class="eleNm" id="polonium" />
            <div class="eleWt">[210]</div>
          </a>
        </td>
        <td id="ele85" class="eleTD">
          <a href="element.html?num=85" id="element85" class="elements halogens r6 c17">
            <div class="eleNum">85</div>
            <div class="eleSym heavyFont">At</div>
            <div class="eleNm" id="astatine" />
            <div class="eleWt">[210]</div>
          </a>
        </td>
        <td id="ele86" class="eleTD">
          <a href="element.html?num=86" id="element86" class="elements nobleGases r6 c18">
            <div class="eleNum">86</div>
            <div class="eleSym heavyFont">Rn</div>
            <div class="eleNm" id="radon" />
            <div class="eleWt">[222]</div>
          </a>
        </td>
      </tr>
      <tr>
        <td id="period7" class="periods unselectable r7 text-center">7</td>
        <td id="ele87" class="eleTD">
          <a href="element.html?num=87" id="element87" class="elements alkaliMetals r7 c1">
            <div class="eleNum">87</div>
            <div class="eleSym heavyFont">Fr</div>
            <div class="eleNm" id="francium" />
            <div class="eleWt">[223]</div>
          </a>
        </td>
        <td id="ele88" class="eleTD">
          <a href="element.html?num=88" id="element88" class="elements alkalineEarthMetals r7 c2">
            <div class="eleNum">88</div>
            <div class="eleSym heavyFont">Ra</div>
            <div class="eleNm" id="radium" />
            <div class="eleWt">[226]</div>
          </a>
        </td>
        <td id="star2" class="text-center">**</td>
        <td id="ele104" class="eleTD">
          <a href="element.html?num=104" id="element104" class="elements transitionMetals r7 c4">
            <div class="eleNum">104</div>
            <div class="eleSym heavyFont">Rf</div>
            <div class="eleNm" id="rutherfordium" />
            <div class="eleWt">[267]</div>
          </a>
        </td>
        <td id="ele105" class="eleTD">
          <a href="element.html?num=105" id="element105" class="elements transitionMetals r7 c5">
            <div class="eleNum">105</div>
            <div class="eleSym heavyFont">Db</div>
            <div class="eleNm" id="dubnium" />
            <div class="eleWt">[268]</div>
          </a>
        </td>
        <td id="ele106" class="eleTD">
          <a href="element.html?num=106" id="element106" class="elements transitionMetals r7 c6">
            <div class="eleNum">106</div>
            <div class="eleSym heavyFont">Sg</div>
            <div class="eleNm" id="seaborgium" />
            <div class="eleWt">[269]</div>
          </a>
        </td>
        <td id="ele107" class="eleTD">
          <a href="element.html?num=107" id="element107" class="elements transitionMetals r7 c7">
            <div class="eleNum">107</div>
            <div class="eleSym heavyFont">Bh</div>
            <div class="eleNm" id="bohrium" />
            <div class="eleWt">[270]</div>
          </a>
        </td>
        <td id="ele108" class="eleTD">
          <a href="element.html?num=108" id="element108" class="elements transitionMetals r7 c8">
            <div class="eleNum">108</div>
            <div class="eleSym heavyFont">Hs</div>
            <div class="eleNm" id="hassium" />
            <div class="eleWt">[269]</div>
          </a>
        </td>
        <td id="ele109" class="eleTD">
          <a href="element.html?num=109" id="element109" class="elements transitionMetals r7 c9">
            <div class="eleNum">109</div>
            <div class="eleSym heavyFont">Mt</div>
            <div class="eleNm" id="meitnerium" />
            <div class="eleWt">[278]</div>
          </a>
        </td>
        <td id="ele110" class="eleTD">
          <a href="element.html?num=110" id="element110" class="elements transitionMetals r7 c10">
            <div class="eleNum">110</div>
            <div class="eleSym heavyFont">Ds</div>
            <div class="eleNm" id="darmstadtium" />
            <div class="eleWt">[281]</div>
          </a>
        </td>
        <td id="ele111" class="eleTD">
          <a href="element.html?num=111" id="element111" class="elements transitionMetals r7 c11">
            <div class="eleNum">111</div>
            <div class="eleSym heavyFont">Rg</div>
            <div class="eleNm" id="roentgenium" />
            <div class="eleWt">[281]</div>
          </a>
        </td>
        <td id="ele112" class="eleTD">
          <a href="element.html?num=112" id="element112" class="elements transitionMetals r7 c12">
            <div class="eleNum">112</div>
            <div class="eleSym heavyFont">Cn</div>
            <div class="eleNm" id="copernicium" />
            <div class="eleWt">[285]</div>
          </a>
        </td>
        <td id="ele113" class="eleTD">
          <a href="element.html?num=113" id="element113" class="elements postTransitionMetals r7 c13">
            <div class="eleNum">113</div>
            <div class="eleSym heavyFont">Nh</div>
            <div class="eleNm" id="nihonium" />
            <div class="eleWt">[286]</div>
          </a>
        </td>
        <td id="ele114" class="eleTD">
          <a href="element.html?num=114" id="element114" class="elements postTransitionMetals r7 c14">
            <div class="eleNum">114</div>
            <div class="eleSym heavyFont">Fl</div>
            <div class="eleNm" id="flerovium" />
            <div class="eleWt">[289]</div>
          </a>
        </td>
        <td id="ele115" class="eleTD">
          <a href="element.html?num=115" id="element115" class="elements postTransitionMetals r7 c15">
            <div class="eleNum">115</div>
            <div class="eleSym heavyFont">Mc</div>
            <div class="eleNm" id="moscovium" />
            <div class="eleWt">[288]</div>
          </a>
        </td>
        <td id="ele116" class="eleTD">
          <a href="element.html?num=116" id="element116" class="elements postTransitionMetals r7 c16">
            <div class="eleNum">116</div>
            <div class="eleSym heavyFont">Lv</div>
            <div class="eleNm" id="livermorium" />
            <div class="eleWt">[293]</div>
          </a>
        </td>
        <td id="ele117" class="eleTD">
          <a href="element.html?num=117" id="element117" class="elements halogens r7 c17">
            <div class="eleNum">117</div>
            <div class="eleSym heavyFont">Ts</div>
            <div class="eleNm" id="tennessine" />
            <div class="eleWt">[294]</div>
          </a>
        </td>
        <td id="ele118" class="eleTD">
          <a href="element.html?num=118" id="element118" class="elements nobleGases r7 c18">
            <div class="eleNum">118</div>
            <div class="eleSym heavyFont">Og</div>
            <div class="eleNm" id="oganesson" />
            <div class="eleWt">[294]</div>
          </a>
        </td>
      </tr>
      <tr>
        <td class="gap" />
      </tr>
      <tr>
        <td />
        <td colspan="2" id="lanthanides" class="text-left"><span>* </span><span id="lanthanidesMain" /></td>
        <td id="ele57" class="eleTD">
          <a href="element.html?num=57" id="element57" class="elements lanthanides r6">
            <div class="eleNum">57</div>
            <div class="eleSym heavyFont">La</div>
            <div class="eleNm" id="lanthanum" />
            <div class="eleWt">138.90547</div>
          </a>
        </td>
        <td id="ele58" class="eleTD">
          <a href="element.html?num=58" id="element58" class="elements lanthanides r6">
            <div class="eleNum">58</div>
            <div class="eleSym heavyFont">Ce</div>
            <div class="eleNm" id="cerium" />
            <div class="eleWt">140.116</div>
          </a>
        </td>
        <td id="ele59" class="eleTD">
          <a href="element.html?num=59" id="element59" class="elements lanthanides r6">
            <div class="eleNum">59</div>
            <div class="eleSym heavyFont">Pr</div>
            <div class="eleNm" id="praseodymium" />
            <div class="eleWt">140.90765</div>
          </a>
        </td>
        <td id="ele60" class="eleTD">
          <a href="element.html?num=60" id="element60" class="elements lanthanides r6">
            <div class="eleNum">60</div>
            <div class="eleSym heavyFont">Nd</div>
            <div class="eleNm" id="neodymium" />
            <div class="eleWt">144.242</div>
          </a>
        </td>
        <td id="ele61" class="eleTD">
          <a href="element.html?num=61" id="element61" class="elements lanthanides r6">
            <div class="eleNum">61</div>
            <div class="eleSym heavyFont">Pm</div>
            <div class="eleNm" id="promethium" />
            <div class="eleWt">[145]</div>
          </a>
        </td>
        <td id="ele62" class="eleTD">
          <a href="element.html?num=62" id="element62" class="elements lanthanides r6">
            <div class="eleNum">62</div>
            <div class="eleSym heavyFont">Sm</div>
            <div class="eleNm" id="samarium" />
            <div class="eleWt">150.36</div>
          </a>
        </td>
        <td id="ele63" class="eleTD">
          <a href="element.html?num=63" id="element63" class="elements lanthanides r6">
            <div class="eleNum">63</div>
            <div class="eleSym heavyFont">Eu</div>
            <div class="eleNm" id="europium" />
            <div class="eleWt">151.964</div>
          </a>
        </td>
        <td id="ele64" class="eleTD">
          <a href="element.html?num=64" id="element64" class="elements lanthanides r6">
            <div class="eleNum">64</div>
            <div class="eleSym heavyFont">Gd</div>
            <div class="eleNm" id="gadolinium" />
            <div class="eleWt">157.25</div>
          </a>
        </td>
        <td id="ele65" class="eleTD">
          <a href="element.html?num=65" id="element65" class="elements lanthanides r6">
            <div class="eleNum">65</div>
            <div class="eleSym heavyFont">Tb</div>
            <div class="eleNm" id="terbium" />
            <div class="eleWt">158.92535</div>
          </a>
        </td>
        <td id="ele66" class="eleTD">
          <a href="element.html?num=66" id="element66" class="elements lanthanides r6">
            <div class="eleNum">66</div>
            <div class="eleSym heavyFont">Dy</div>
            <div class="eleNm" id="dysprosium" />
            <div class="eleWt">162.5</div>
          </a>
        </td>
        <td id="ele67" class="eleTD">
          <a href="element.html?num=67" id="element67" class="elements lanthanides r6">
            <div class="eleNum">67</div>
            <div class="eleSym heavyFont">Ho</div>
            <div class="eleNm" id="holmium" />
            <div class="eleWt">164.93032</div>
          </a>
        </td>
        <td id="ele68" class="eleTD">
          <a href="element.html?num=68" id="element68" class="elements lanthanides r6">
            <div class="eleNum">68</div>
            <div class="eleSym heavyFont">Er</div>
            <div class="eleNm" id="erbium" />
            <div class="eleWt">167.259</div>
          </a>
        </td>
        <td id="ele69" class="eleTD">
          <a href="element.html?num=69" id="element69" class="elements lanthanides r6">
            <div class="eleNum">69</div>
            <div class="eleSym heavyFont">Tm</div>
            <div class="eleNm" id="thulium" />
            <div class="eleWt">168.93421</div>
          </a>
        </td>
        <td id="ele70" class="eleTD">
          <a href="element.html?num=70" id="element70" class="elements lanthanides r6">
            <div class="eleNum">70</div>
            <div class="eleSym heavyFont">Yb</div>
            <div class="eleNm" id="ytterbium" />
            <div class="eleWt">173.054</div>
          </a>
        </td>
        <td id="ele71" class="eleTD">
          <a href="element.html?num=71" id="element71" class="elements lanthanides r6">
            <div class="eleNum">71</div>
            <div class="eleSym heavyFont">Lu</div>
            <div class="eleNm" id="lutetium" />
            <div class="eleWt">174.9668</div>
          </a>
        </td>
      </tr>
      <tr>
        <td />
        <td colspan="2" id="actinides" class="text-left"><span>** </span><span id="actinidesMain" /></td>
        <td id="ele89" class="eleTD">
          <a href="element.html?num=89" id="element89" class="elements actinides r7">
            <div class="eleNum">89</div>
            <div class="eleSym heavyFont">Ac</div>
            <div class="eleNm" id="actinium" />
            <div class="eleWt">[227]</div>
          </a>
        </td>
        <td id="ele90" class="eleTD">
          <a href="element.html?num=90" id="element90" class="elements actinides r7">
            <div class="eleNum">90</div>
            <div class="eleSym heavyFont">Th</div>
            <div class="eleNm" id="thorium" />
            <div class="eleWt">232.03806</div>
          </a>
        </td>
        <td id="ele91" class="eleTD">
          <a href="element.html?num=91" id="element91" class="elements actinides r7">
            <div class="eleNum">91</div>
            <div class="eleSym heavyFont">Pa</div>
            <div class="eleNm" id="protactinium" />
            <div class="eleWt">231.03588</div>
          </a>
        </td>
        <td id="ele92" class="eleTD">
          <a href="element.html?num=92" id="element92" class="elements actinides r7">
            <div class="eleNum">92</div>
            <div class="eleSym heavyFont">U</div>
            <div class="eleNm" id="uranium" />
            <div class="eleWt">238.02891</div>
          </a>
        </td>
        <td id="ele93" class="eleTD">
          <a href="element.html?num=93" id="element93" class="elements actinides r7">
            <div class="eleNum">93</div>
            <div class="eleSym heavyFont">Np</div>
            <div class="eleNm" id="neptunium" />
            <div class="eleWt">[237]</div>
          </a>
        </td>
        <td id="ele94" class="eleTD">
          <a href="element.html?num=94" id="element94" class="elements actinides r7">
            <div class="eleNum">94</div>
            <div class="eleSym heavyFont">Pu</div>
            <div class="eleNm" id="plutonium" />
            <div class="eleWt">[244]</div>
          </a>
        </td>
        <td id="ele95" class="eleTD">
          <a href="element.html?num=95" id="element95" class="elements actinides r7">
            <div class="eleNum">95</div>
            <div class="eleSym heavyFont">Am</div>
            <div class="eleNm" id="americium" />
            <div class="eleWt">[243]</div>
          </a>
        </td>
        <td id="ele96" class="eleTD">
          <a href="element.html?num=96" id="element96" class="elements actinides r7">
            <div class="eleNum">96</div>
            <div class="eleSym heavyFont">Cm</div>
            <div class="eleNm" id="curium" />
            <div class="eleWt">[247]</div>
          </a>
        </td>
        <td id="ele97" class="eleTD">
          <a href="element.html?num=97" id="element97" class="elements actinides r7">
            <div class="eleNum">97</div>
            <div class="eleSym heavyFont">Bk</div>
            <div class="eleNm" id="berkelium" />
            <div class="eleWt">[247]</div>
          </a>
        </td>
        <td id="ele98" class="eleTD">
          <a href="element.html?num=98" id="element98" class="elements actinides r7">
            <div class="eleNum">98</div>
            <div class="eleSym heavyFont">Cf</div>
            <div class="eleNm" id="californium" />
            <div class="eleWt">[251]</div>
          </a>
        </td>
        <td id="ele99" class="eleTD">
          <a href="element.html?num=99" id="element99" class="elements actinides r7">
            <div class="eleNum">99</div>
            <div class="eleSym heavyFont">Es</div>
            <div class="eleNm" id="einsteinium" />
            <div class="eleWt">[252]</div>
          </a>
        </td>
        <td id="ele100" class="eleTD">
          <a href="element.html?num=100" id="element100" class="elements actinides r7">
            <div class="eleNum">100</div>
            <div class="eleSym heavyFont">Fm</div>
            <div class="eleNm" id="fermium" />
            <div class="eleWt">[257]</div>
          </a>
        </td>
        <td id="ele101" class="eleTD">
          <a href="element.html?num=101" id="element101" class="elements actinides r7">
            <div class="eleNum">101</div>
            <div class="eleSym heavyFont">Md</div>
            <div class="eleNm" id="mendelevium" />
            <div class="eleWt">[258]</div>
          </a>
        </td>
        <td id="ele102" class="eleTD">
          <a href="element.html?num=102" id="element102" class="elements actinides r7">
            <div class="eleNum">102</div>
            <div class="eleSym heavyFont">No</div>
            <div class="eleNm" id="nobelium" />
            <div class="eleWt">[259]</div>
          </a>
        </td>
        <td id="ele103" class="eleTD">
          <a href="element.html?num=103" id="element103" class="elements actinides r7">
            <div class="eleNum">103</div>
            <div class="eleSym heavyFont">Lr</div>
            <div class="eleNm" id="lawrencium" />
            <div class="eleWt">[262]</div>
          </a>
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
