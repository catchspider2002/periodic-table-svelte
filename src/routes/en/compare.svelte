<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import Constants from "../../components/constants.js";

  let langValue = "en";
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
    let selectedElement = newRawData.find((x) => x.id === val);
    if (selectedElement) return selectedElement;
    else return newRawData[0];
  }

  function getNum(value) {
    if (langValue === "ar") {
      // Arabic
      value = value.toString().replace(/\./g, "٫");
      var id = ["٠", "١", "٢", "٣", "٤", "٥", "٦", "٧", "٨", "٩"];
      return value.toString().replace(/[0-9]/g, function (w) {
        return id[+w];
      });
    } else if (langValue === "fa") {
      // Persian
      value = value.toString().replace(/\./g, "٫");
      var id = ["۰", "۱", "۲", "۳", "۴", "۵", "۶", "۷", "۸", "۹"];
      return value.toString().replace(/[0-9]/g, function (w) {
        return id[+w];
      });
    } else return value;
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
            <a href="{langValue}/{firstEle.nme}">
              <div class="col-xs-4 new-table compareLink"><span class="underlineLink">{Lang[firstEle.nme]}</span></div>
            </a>
            <a href="{langValue}/{secondEle.nme}">
              <div class="col-xs-4 new-table compareLink"><span class="underlineLink">{Lang[secondEle.nme]}</span></div>
            </a>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelSymbol}</div>
            <div class="col-xs-4 new-table">{firstEle.sym}</div>
            <div class="col-xs-4 new-table">{secondEle.sym}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelAtmNoMain}</div>
            <div class="col-xs-4 new-table">{getNum(firstEle.num)}</div>
            <div class="col-xs-4 new-table">{getNum(secondEle.num)}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.group}</div>
            <div class="col-xs-4 new-table">
              {#if firstEle.grp === 'na'}{Lang.na}{:else}{getNum(firstEle.grp)}{/if}
            </div>
            <div class="col-xs-4 new-table">
              {#if secondEle.grp === 'na'}{Lang.na}{:else}{getNum(secondEle.grp)}{/if}
            </div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.period}</div>
            <div class="col-xs-4 new-table">{getNum(firstEle.prd)}</div>
            <div class="col-xs-4 new-table">{getNum(secondEle.prd)}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.block}</div>
            <div class="col-xs-4 new-table">{firstEle.blk}</div>
            <div class="col-xs-4 new-table">{secondEle.blk}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen">{Lang.labelCrustMain}</div>
            <div class="col-xs-4 new-table">
              {#if firstEle.crt === 'na'}
                {Lang.na}
              {:else}
                {@html getNum(firstEle.crt)}
              {/if}
            </div>
            <div class="col-xs-4 new-table">
              {#if secondEle.crt === 'na'}
                {Lang.na}
              {:else}
                {@html getNum(secondEle.crt)}
              {/if}
            </div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen">{Lang.labelUniverseMain}</div>
            <div class="col-xs-4 new-table">
              {#if firstEle.uni === 'na'}
                {Lang.na}
              {:else}
                {@html getNum(firstEle.uni)}
              {/if}
            </div>
            <div class="col-xs-4 new-table">
              {#if secondEle.uni === 'na'}
                {Lang.na}
              {:else}
                {@html getNum(secondEle.uni)}
              {/if}
            </div>
          </div>
          <div class="padding-top-42">
            <div class="headerOutline text-upper heavyFont">{Lang.labelGeneralProp}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelAtmWtMain}</div>
            <div id="atmWeight1" class="col-xs-4 new-table">{getNum(firstEle.aWt)}</div>
            <div id="atmWeight2" class="col-xs-4 new-table">{getNum(secondEle.aWt)}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelCategoryMain}</div>
            <div class="col-xs-4 new-table">{Lang[firstEle.ctg]}</div>
            <div class="col-xs-4 new-table">{Lang[secondEle.ctg]}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelColorMain}</div>
            <div class="col-xs-4 new-table">{Lang[firstEle.clr]}</div>
            <div class="col-xs-4 new-table">{Lang[secondEle.clr]}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelRadioMain}</div>
            <div class="col-xs-4 new-table">{Lang[firstEle.rdo]}</div>
            <div class="col-xs-4 new-table">{Lang[secondEle.rdo]}</div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont">{Lang.labelStructureMain}</div>
            <div class="col-xs-4 new-table">{Lang[firstEle.stc]}</div>
            <div class="col-xs-4 new-table">{Lang[secondEle.stc]}</div>
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
            <div id="fusion1" class="col-xs-4 new-table">
              {#if firstEle.fsn === 'na'}{Lang.na}{:else}{getNum(firstEle.fsn)}{/if}
            </div>
            <div id="fusion2" class="col-xs-4 new-table">
              {#if secondEle.fsn === 'na'}{Lang.na}{:else}{getNum(secondEle.fsn)}{/if}
            </div>
          </div>
          <div class="row">
            <div class="col-xs-4 new-table heavyFont hyphen"><span>{Lang.labelVaporizationMain}</span> (<span>{Lang.labelFusion}</span>)</div>
            <div id="vaporization1" class="col-xs-4 new-table">
              {#if firstEle.vpn === 'na'}{Lang.na}{:else}{getNum(firstEle.vpn)}{/if}
            </div>
            <div id="vaporization2" class="col-xs-4 new-table">
              {#if secondEle.vpn === 'na'}{Lang.na}{:else}{getNum(secondEle.vpn)}{/if}
            </div>
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
