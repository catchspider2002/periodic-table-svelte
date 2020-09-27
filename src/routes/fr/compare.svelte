<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import Constants from "../../components/constants.js";

  let newRawData = Constants;
  let firstElement = 0,
    secondElement = 0;

  newRawData.sort(function (a, b) {
    if (Lang[a.nme] < Lang[b.nme]) return -1;
    else if (Lang[a.nme] > Lang[b.nme]) return 1;
    return 0;
  });

  let firstEle = getElement(firstElement);
  let secondEle = getElement(firstElement);

  function getElement(val) {
    console.log(val);
    let selectedElement = newRawData.find((x) => x.id === val);
    if (selectedElement) return selectedElement;
    else return newRawData[0];
  }
</script>

<div class="content-wrapper">
  <div class="container">
    <div class="row">
      <div id="compareBg" class="box-content">
        <div id="mainCompare">
          <div id="topRowCompare">
            <div id="compareTop" class="square">
              <div class="col-xs-4 new-table" />
              <div class="col-xs-4 new-table padding-10">
                <!-- <select id="firstElement" aria-label="First Element" /> -->
                <!-- <select aria-label="First Element" bind:value={selected} on:change="{() => answer = ''}"> -->
                <select aria-label="First Element" bind:value={firstElement} on:change={() => (firstEle = getElement(firstElement))}>
                  {#each newRawData as ele}
                    <option value={ele.id}>{Lang[ele.nme]}</option>
                  {/each}
                </select>
              </div>
              <div class="col-xs-4 new-table padding-10">
                <select aria-label="Second Element" bind:value={secondElement} on:change={() => (secondEle = getElement(secondElement))}>
                  {#each newRawData as ele}
                    <option value={ele.id}>{Lang[ele.nme]}</option>
                  {/each}
                </select>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelName}</div>
            <a id="compEle1">
              <div class="col-xs-4 new-table compareLink"><span id="name1" class="underlineLink">{Lang[firstEle.nme]}</span></div>
            </a>
            <a id="compEle2">
              <div class="col-xs-4 new-table compareLink"><span id="name2" class="underlineLink">{Lang[secondEle.nme]}</span></div>
            </a>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelSymbol}</div>
            <div id="symbol1" class="col-xs-4 new-table" />
            <div id="symbol2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelAtmNoMain}</div>
            <div id="atmNo1" class="col-xs-4 new-table" />
            <div id="atmNo2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.group}</div>
            <div id="groups1" class="col-xs-4 new-table" />
            <div id="groups2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.period}</div>
            <div id="periods1" class="col-xs-4 new-table" />
            <div id="periods2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.block}</div>
            <div id="block1" class="col-xs-4 new-table" />
            <div id="block2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen">{Lang.labelCrustMain}</div>
            <div id="crust1" class="col-xs-4 new-table" />
            <div id="crust2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen">{Lang.labelUniverseMain}</div>
            <div id="universe1" class="col-xs-4 new-table" />
            <div id="universe2" class="col-xs-4 new-table" />
          </div>
          <div class="padding-top-42">
            <div class="headerOutline text-upper heavyFont">{Lang.labelGeneralProp}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelAtmWtMain}</div>
            <div id="atmWeight1" class="col-xs-4 new-table" />
            <div id="atmWeight2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelCategoryMain}</div>
            <div id="category1" class="col-xs-4 new-table" />
            <div id="category2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelColorMain}</div>
            <div id="eleColor1" class="col-xs-4 new-table" />
            <div id="eleColor2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelRadioMain}</div>
            <div id="radioactive1" class="col-xs-4 new-table" />
            <div id="radioactive2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelStructureMain}</div>
            <div id="structure1" class="col-xs-4 new-table" />
            <div id="structure2" class="col-xs-4 new-table" />
          </div>
          <div class="padding-top-42">
            <div class="headerOutline text-upper heavyFont">{Lang.labelPhysicalProp}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">
              <span>{Lang.labelDensityMain}</span> (<span>{@html Lang.labelDensity}</span>)
            </div>
            <div id="density1" class="col-xs-4 new-table" />
            <div id="density2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelPhaseMain}</div>
            <div id="phase1" class="col-xs-4 new-table" />
            <div id="phase2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelMeltingMain}</div>
            <div id="meltPoint1" class="col-xs-4 new-table" />
            <div id="meltPoint2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelBoilingMain}</div>
            <div id="boilPoint1" class="col-xs-4 new-table" />
            <div id="boilPoint2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont"><span>{Lang.labelFusionMain}</span> (<span>{Lang.labelFusion}</span>)</div>
            <div id="fusion1" class="col-xs-4 new-table" />
            <div id="fusion2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen"><span>{Lang.labelVaporizationMain}</span> (<span>{Lang.labelFusion}</span>)</div>
            <div id="vaporization1" class="col-xs-4 new-table" />
            <div id="vaporization2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen"><span>{Lang.labelSpecificMain}</span> (<span>{Lang.labelSpecific}</span>)</div>
            <div id="spHeat1" class="col-xs-4 new-table" />
            <div id="spHeat2" class="col-xs-4 new-table" />
          </div>
          <div class="padding-top-42">
            <div class="headerOutline text-upper heavyFont">{Lang.labelAtomicProp}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelRadiusMain}</div>
            <div id="atmRadius1" class="col-xs-4 new-table" />
            <div id="atmRadius2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelCovalentMain}</div>
            <div id="covRadius1" class="col-xs-4 new-table" />
            <div id="covRadius2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen"><span>{Lang.labelElectronegativityMain}</span> (<span>{Lang.pauling}</span>)</div>
            <div id="eleNeg1" class="col-xs-4 new-table" />
            <div id="eleNeg2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen"><span>{Lang.labelIonizationMain}</span> (<span>{Lang.labelIonization}</span>)</div>
            <div id="ionization1" class="col-xs-4 new-table" />
            <div id="ionization2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">
              <span>{Lang.labelVolumeMain}</span> (<span>{@html Lang.labelVolume}</span>)
            </div>
            <div id="volume1" class="col-xs-4 new-table" />
            <div id="volume2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen"><span>{Lang.labelThermalMain}</span> (<span>{Lang.labelThermal}</span>)</div>
            <div id="theCond1" class="col-xs-4 new-table" />
            <div id="theCond2" class="col-xs-4 new-table" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen">{Lang.labelOxidationMain}</div>
            <div id="oxidation1" class="col-xs-4 new-table ltrText text-left" />
            <div id="oxidation2" class="col-xs-4 new-table ltrText text-left" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen">{Lang.labelConfigMain}</div>
            <div id="elecConfig1" class="col-xs-4 new-table ltrText text-left" />
            <div id="elecConfig2" class="col-xs-4 new-table ltrText text-left" />
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelElectronsMain}</div>
            <div id="electrons1" class="col-xs-4 new-table ltrText text-left" />
            <div id="electrons2" class="col-xs-4 new-table ltrText text-left" />
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="footer">
  <Footer />
</div>
