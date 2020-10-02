<script>
  import Lang from "./locale.js";
  import LangDropdown from "../../components/LanguageDropdown.svelte";
  function langChange() {
    console.log(selected);
  }
  let selected = "en";
</script>

<style>
  .modal-dialog {
    text-transform: capitalize;
  }
</style>

<div class="modal-dialog" role="document">
  <div class="modal-content">
    <div class="modal-inner">
      <div class="modal-header">
        <span id="modalSettings" class="modal-title text-left text-upper heavyFont">{Lang.settings}</span>
        <!-- <button type="button" class="close" data-dismiss="modal" aria-label="Close"> <span aria-hidden="true">&times;</span> </button> -->
      </div>
      <div class="modal-body">
        <div class="grid grid-row-gap-10 items-center">
          <div class="new-table heavyFont text-left" id="language">{Lang.language}</div>
          <div class="new-table">
            <LangDropdown />
          </div>
          <div class="new-table heavyFont text-left self-start">{Lang.temperature}</div>
          <div class="radio-toolbar padding-top-5">
            <input type="radio" id="tempcelsius" name="temperature" value="celsius" onchange="setTemp()" />
            <label class="disable-select" for="tempcelsius">{Lang.tempCelsius}</label>
            <input type="radio" id="tempfahrenheit" name="temperature" value="fahrenheit" onchange="setTemp()" />
            <label class="disable-select" for="tempfahrenheit">{Lang.tempFahrenheit}</label>
          </div>
          <div class="new-table heavyFont padding-top-5 text-left self-start">{Lang.labelColorMain}</div>
          <div class="new-table">
            <table id="colorTable">
              <tbody>
                <tr>
                  <td id="color1" class="colorClass" title="Red" />
                  <td id="color2" class="colorClass" title="Orange" />
                  <td id="color3" class="colorClass" title="Yellow" />
                  <td id="color4" class="colorClass" title="Brown" />
                  <td id="color5" class="colorClass" title="Lime" />
                </tr>
                <tr>
                  <td id="color6" class="colorClass" title="Green" />
                  <td id="color7" class="colorClass" title="Cyan" />
                  <td id="color8" class="colorClass" title="Blue" />
                  <td id="color9" class="colorClass" title="Purple" />
                  <td id="color10" class="colorClass" title="Pink" />
                </tr>
              </tbody>
            </table>
          </div>
          <div id="settingPeriodicTable" class="new-table span-2" />
          <div class="new-table heavyFont text-left">{Lang.tableWidth}</div>
          <div class="new-table">
            <select id="marginSetting" aria-label="Table Width">
              <option value="1">100%</option>
              <option value="0.95">95%</option>
              <option value="0.9">90%</option>
              <option value="0.85">85%</option>
              <option value="0.8">80%</option>
            </select>
          </div>
          <div class="new-table heavyFont text-left">{Lang.labelName}</div>
          <div class="new-table text-left padding-top-5">
            <label class="switch"> <input id="nameSelectSetting" type="checkbox" /> <span class="slider round" /> </label>
          </div>
          <div class="new-table heavyFont text-left">{Lang.labelAtmWtMain}</div>
          <div class="new-table text-left padding-top-5">
            <label class="switch"> <input id="atmNoSelectSetting" type="checkbox" /> <span class="slider round" /> </label>
          </div>
          <div class="new-table heavyFont text-left self-start" id="tableStyle">Style</div>
          <div class="radio-toolbar radio-style padding-top-5">
            <input type="radio" id="style1" name="tableStyle" value="1" onchange="setStyle()" />
            <label id="style1Label" class="disable-select" for="style1" />
            <input type="radio" id="style2" name="tableStyle" value="2" onchange="setStyle()" />
            <label id="style2Label" class="disable-select" for="style2" />
            <input type="radio" id="style3" name="tableStyle" value="3" onchange="setStyle()" />
            <label id="style3Label" class="disable-select" for="style3" />
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
