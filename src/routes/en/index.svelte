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
  import Footer from "./_Footer.svelte";
  import Element from "../../components/Element.svelte";
  import Lang from "./locale.js";
  import Nav from "./_Nav.svelte";
  import { onMount } from "svelte";
  let langValue = Lang.lang;

  let color1 = "253, 58, 74";
  let color2 = "245, 128, 37";
  let color3 = "255, 167, 0";
  let color4 = "123, 113, 81";
  let color5 = "91, 170, 9";
  let color6 = "26, 152, 90";
  let color7 = "59, 168, 221";
  let color8 = "0, 120, 215";
  let color9 = "139, 102, 204";
  let color10 = "228, 27, 144";

  onMount(async () => {
    // console.log("On Mount");
    singleElement = cls("elements");
    singleGroup = cls("groups");
    singlePeriod = cls("periods");
    singleCategory = cls("category");

    elementLength = singleElement.length;
    categoryLength = singleCategory.length;
    periodLength = singlePeriod.length;
    groupLength = singleGroup.length;

    for (var i = 0; i < elementLength; i++) {
      singleElement[i].addEventListener("mouseenter", setOutline, false);
      singleElement[i].addEventListener("mouseleave", removeOutline, false);
    }

    for (var i = 0; i < categoryLength; i++) {
      singleCategory[i].addEventListener("mouseenter", setOpacity15, false);
      singleCategory[i].addEventListener("mouseleave", setOpacity100, false);
    }

    for (var i = 0; i < periodLength; i++) {
      if (langValue === "ar" || langValue === "fa" || langValue === "he") singlePeriod[i].textContent = getNum(singlePeriod[i].textContent);
      singlePeriod[i].addEventListener("mouseenter", setOpacity15, false);
      singlePeriod[i].addEventListener("mouseleave", setOpacity100, false);
    }

    for (var i = 0; i < groupLength; i++) {
      if (langValue === "ar" || langValue === "fa" || langValue === "he") singleGroup[i].textContent = getNum(singleGroup[i].textContent);
      singleGroup[i].addEventListener("mouseenter", setOpacity15, false);
      singleGroup[i].addEventListener("mouseleave", setOpacity100, false);
    }

    if (langValue === "ar" || langValue === "fa" || langValue === "he") {
      for (var i = 0; i < singleNum.length; i++) singleNum[i].textContent = getNum(singleNum[i].textContent);

      for (var i = 0; i < singleWt.length; i++) singleWt[i].textContent = getNum(singleWt[i].textContent);
    }
  });

  let singleElement, singleGroup, singlePeriod, singleCategory;

  let elementLength, categoryLength, periodLength, groupLength;

  function id(text) {
    return document.getElementById(text);
  }

  function cls(classId) {
    return document.getElementsByClassName(classId);
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

  function getTemp(tempValue) {
    var newTemp;
    let defaultTemp = localStorage.getItem("defaultTemp");
    let defaultPunc = "dot";

    if (tempValue == "-") newTemp = "-";
    else {
      if (langValue === "ar" || langValue === "fa" || langValue === "he")
        newTemp =
          getNum(Math.round((tempValue + 273.15) * 100) / 100) +
          " K " +
          (defaultTemp == "celsius" ? getNum(tempValue) + " | °C" : getNum(Math.round((tempValue * 1.8 + 32) * 100) / 100) + " °F");
      else
        newTemp =
          Math.round((tempValue + 273.15) * 100) / 100 +
          " K | " +
          (defaultTemp == "celsius" ? tempValue + " °C" : Math.round((tempValue * 1.8 + 32) * 100) / 100 + " °F");
    }

    if (defaultPunc === "comma") newTemp = newTemp.replace(/\./g, ",");

    return newTemp;
  }

  function setOpacity(percent) {
    for (var i = 0; i < singleElement.length; i++) singleElement[i].style.opacity = percent;
    for (var i = 0; i < singleCategory.length; i++) singleCategory[i].style.opacity = percent;
    for (var i = 0; i < singleGroup.length; i++) singleGroup[i].style.opacity = percent;
    for (var i = 0; i < singlePeriod.length; i++) singlePeriod[i].style.opacity = percent;
    id("lanthanidesMain").style.opacity = percent;
    id("actinidesMain").style.opacity = percent;
    id("star1").style.opacity = percent;
    id("star2").style.opacity = percent;
    id("groupHeader").style.opacity = percent;
    id("periodHeader").style.opacity = percent;
  }

  function setOpacity100() {
    setOpacity(1);
  }

  function setOpacity15() {
    var className = this.id;
    let classVal = className;
    let classes = cls(classVal);
    setOpacity(0.15);
    for (var i = 0; i < classes.length; i++) classes[i].style.opacity = 1;
    if (
      className === "r1" ||
      className === "r2" ||
      className === "r3" ||
      className === "r4" ||
      className === "r5" ||
      className === "r6" ||
      className === "r7"
    )
      id("periodHeader").style.opacity = 1;
    if (
      className === "c1" ||
      className === "c2" ||
      className === "c3" ||
      className === "c4" ||
      className === "c5" ||
      className === "c6" ||
      className === "c7" ||
      className === "c8" ||
      className === "c9" ||
      className === "c10" ||
      className === "c11" ||
      className === "c12" ||
      className === "c13" ||
      className === "c14" ||
      className === "c15" ||
      className === "c16" ||
      className === "c17" ||
      className === "c18"
    )
      id("groupHeader").style.opacity = 1;
  }

  function setOutline() {
    var element = this.id;
    var tempClass = id(element).className.replace("elements ", "");
    var colClass = tempClass.substring(0, tempClass.indexOf(" "));
    var elementColor;

    switch (colClass) {
      case "alkaliMetals":
        elementColor = "rgba(" + color10 + ",0.5)";
        break;
      case "alkalineEarthMetals":
        elementColor = "rgba(" + color8 + ",0.5)";
        break;
      case "transitionMetals":
        elementColor = "rgba(" + color1 + ",0.5)";
        break;
      case "postTransitionMetals":
        elementColor = "rgba(" + color9 + ",0.5)";
        break;
      case "otherNonmetals":
        elementColor = "rgba(" + color6 + ",0.5)";
        break;
      case "metalloids":
        elementColor = "rgba(" + color2 + ",0.5)";
        break;
      case "halogens":
        elementColor = "rgba(" + color7 + ",0.5)";
        break;
      case "nobleGases":
        elementColor = "rgba(" + color5 + ",0.5)";
        break;
      case "lanthanides":
        elementColor = "rgba(" + color3 + ",0.5)";
        break;
      case "actinides":
        elementColor = "rgba(" + color4 + ",0.5)";
        break;
    }

    if (document.documentElement.getAttribute("data-style") === "2") {
      id("snippet").style.backgroundColor = "transparent";
      id("details").style.backgroundColor = "transparent";
      id("snippet").style.border = "none";
      id("details").style.border = "none";
      id("snippet").style.borderBottom = "0.125em solid " + elementColor;
      id("details").style.borderBottom = "0.125em solid " + elementColor;
    } else if (document.documentElement.getAttribute("data-style") === "3") {
      id("snippet").style.backgroundColor = "transparent";
      id("details").style.backgroundColor = "transparent";
      id("snippet").style.border = "0.125em solid " + elementColor;
      id("details").style.border = "0.125em solid " + elementColor;
    } else {
      id("snippet").style.backgroundColor = elementColor;
      id("details").style.backgroundColor = elementColor;
      id("snippet").style.border = "none";
      id("details").style.border = "none";
    }
    var eleId = Constants[element.replace("element", "")];

    id("snippetNum").innerHTML = getNum(eleId.num);
    id("snippetSym").innerHTML = eleId.sym;
    id("snippetWt").innerHTML = getNum(eleId.aWt).toString();
    id("detailRow1").innerHTML = Lang[eleId.nme];
    var eleYear = eleId.yr + "";

    if (eleYear.indexOf(" ") > 0) {
      if (langValue === "zs") eleYear = "公元前" + eleYear.substring(0, eleYear.indexOf(" ")) + "年";
      else if (langValue === "ko") eleYear = "기원전 " + eleYear.substring(0, eleYear.indexOf(" ")) + "년";
      else if (langValue === "ja") eleYear = "紀元前" + eleYear.substring(0, eleYear.indexOf(" ")) + "年";
      else if (langValue === "kk") eleYear = "б.з.д" + eleYear.substring(0, eleYear.indexOf(" ")) + "ж.";
      else if (langValue === "hu" || langValue === "tr" || langValue === "ms" || langValue === "th")
        eleYear = Lang.BC + " " + eleYear.substring(0, eleYear.indexOf(" "));
      else eleYear = eleYear.substring(0, eleYear.indexOf(" ")) + " " + Lang.BC;
    } else {
      if (langValue === "ko") eleYear = eleYear + "년";
    }

    id("valueRow2").innerHTML = eleYear;
    id("valueRow3").innerHTML = getTemp(eleId.mlt);
    id("valueRow4").innerHTML = getTemp(eleId.bln);
    id("valueRow5").innerHTML = getNum(eleId.elc);
    id("valueRow6").innerHTML = eleId.cnf;
    id(element).style.outline = "2px solid #505050";
    id(element).style.opacity = "0.75";
    id("snippetDetails").style.visibility = "visible";
  }

  function removeOutline() {
    var element = this.id;
    if (id("snippet")) {
      id(element).style.outline = "none";
      id("snippetDetails").style.visibility = "hidden";
      id(element).style.opacity = "1";
    }
  }
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
        <td id="c1" class="groups unselectable c1">1</td>
        <td id="c2" class="groups unselectable c2">2</td>
        <td id="c3" class="groups unselectable c3">3</td>
        <td id="c4" class="groups unselectable c4">4</td>
        <td id="c5" class="groups unselectable c5">5</td>
        <td id="c6" class="groups unselectable c6">6</td>
        <td id="c7" class="groups unselectable c7">7</td>
        <td id="c8" class="groups unselectable c8">8</td>
        <td id="c9" class="groups unselectable c9">9</td>
        <td id="c10" class="groups unselectable c10">10</td>
        <td id="c11" class="groups unselectable c11">11</td>
        <td id="c12" class="groups unselectable c12">12</td>
        <td id="c13" class="groups unselectable c13">13</td>
        <td id="c14" class="groups unselectable c14">14</td>
        <td id="c15" class="groups unselectable c15">15</td>
        <td id="c16" class="groups unselectable c16">16</td>
        <td id="c17" class="groups unselectable c17">17</td>
        <td id="c18" class="groups unselectable c18">18</td>
        <td id="c19" class="groups unselectable" />
      </tr>
      <tr>
        <td id="r1" class="periods unselectable r1 text-center">1</td>
        <Element {langValue} name={Lang[Constants[0].nme]} num="0" className="otherNonmetals r1 c1" />
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
              <div id="detailRow2">{Lang.discovered}</div>
              <div id="valueRow2" />
              <div id="detailRow3">{Lang.labelMeltingMain}</div>
              <div id="valueRow3" />
              <div id="detailRow4">{Lang.labelBoilingMain}</div>
              <div id="valueRow4" />
              <div id="detailRow5">{Lang.labelElectronsMain}</div>
              <div id="valueRow5" class="ltrText text-left" />
              <div id="detailRow6">{Lang.labelConfigMain}</div>
              <div id="valueRow6" class="ltrText text-left" />
            </div>
          </div>
        </td>
        <td colspan="5" />
        <Element {langValue} name={Lang[Constants[1].nme]} num="1" className="nobleGases r1 c18" />
      </tr>
      <tr>
        <td id="r2" class="periods unselectable r2 text-center">2</td>
        <Element {langValue} name={Lang[Constants[2].nme]} num="2" className="alkaliMetals r2 c1" />
        <Element {langValue} name={Lang[Constants[3].nme]} num="3" className="alkalineEarthMetals r2 c2" />
        <Element {langValue} name={Lang[Constants[4].nme]} num="4" className="metalloids r2 c13" />
        <Element {langValue} name={Lang[Constants[5].nme]} num="5" className="otherNonmetals r2 c14" />
        <Element {langValue} name={Lang[Constants[6].nme]} num="6" className="otherNonmetals r2 c15" />
        <Element {langValue} name={Lang[Constants[7].nme]} num="7" className="otherNonmetals r2 c16" />
        <Element {langValue} name={Lang[Constants[8].nme]} num="8" className="halogens r2 c17" />
        <Element {langValue} name={Lang[Constants[9].nme]} num="9" className="nobleGases r2 c18" />
      </tr>
      <tr>
        <td id="r3" class="periods unselectable r3 text-center">3</td>
        <Element {langValue} name={Lang[Constants[10].nme]} num="10" className="alkaliMetals r3 c1" />
        <Element {langValue} name={Lang[Constants[11].nme]} num="11" className="alkalineEarthMetals r3 c2" />
        <Element {langValue} name={Lang[Constants[12].nme]} num="12" className="postTransitionMetals r3 c13" />
        <Element {langValue} name={Lang[Constants[13].nme]} num="13" className="metalloids r3 c14" />
        <Element {langValue} name={Lang[Constants[14].nme]} num="14" className="otherNonmetals r3 c15" />
        <Element {langValue} name={Lang[Constants[15].nme]} num="15" className="otherNonmetals r3 c16" />
        <Element {langValue} name={Lang[Constants[16].nme]} num="16" className="halogens r3 c17" />
        <Element {langValue} name={Lang[Constants[17].nme]} num="17" className="nobleGases r3 c18" />
      </tr>
      <tr>
        <td id="r4" class="periods unselectable r4 text-center">4</td>
        <Element {langValue} name={Lang[Constants[18].nme]} num="18" className="alkaliMetals r4 c1" />
        <Element {langValue} name={Lang[Constants[19].nme]} num="19" className="alkalineEarthMetals r4 c2" />
        <Element {langValue} name={Lang[Constants[20].nme]} num="20" className="transitionMetals r4 c3" />
        <Element {langValue} name={Lang[Constants[21].nme]} num="21" className="transitionMetals r4 c4" />
        <Element {langValue} name={Lang[Constants[22].nme]} num="22" className="transitionMetals r4 c5" />
        <Element {langValue} name={Lang[Constants[23].nme]} num="23" className="transitionMetals r4 c6" />
        <Element {langValue} name={Lang[Constants[24].nme]} num="24" className="transitionMetals r4 c7" />
        <Element {langValue} name={Lang[Constants[25].nme]} num="25" className="transitionMetals r4 c8" />
        <Element {langValue} name={Lang[Constants[26].nme]} num="26" className="transitionMetals r4 c9" />
        <Element {langValue} name={Lang[Constants[27].nme]} num="27" className="transitionMetals r4 c10" />
        <Element {langValue} name={Lang[Constants[28].nme]} num="28" className="transitionMetals r4 c11" />
        <Element {langValue} name={Lang[Constants[29].nme]} num="29" className="transitionMetals r4 c12" />
        <Element {langValue} name={Lang[Constants[30].nme]} num="30" className="postTransitionMetals r4 c13" />
        <Element {langValue} name={Lang[Constants[31].nme]} num="31" className="metalloids r4 c14" />
        <Element {langValue} name={Lang[Constants[32].nme]} num="32" className="metalloids r4 c15" />
        <Element {langValue} name={Lang[Constants[33].nme]} num="33" className="otherNonmetals r4 c16" />
        <Element {langValue} name={Lang[Constants[34].nme]} num="34" className="halogens r4 c17" />
        <Element {langValue} name={Lang[Constants[35].nme]} num="35" className="nobleGases r4 c18" />
      </tr>
      <tr>
        <td id="r5" class="periods unselectable r5 text-center">5</td>
        <Element {langValue} name={Lang[Constants[36].nme]} num="36" className="alkaliMetals r5 c1" />
        <Element {langValue} name={Lang[Constants[37].nme]} num="37" className="alkalineEarthMetals r5 c2" />
        <Element {langValue} name={Lang[Constants[38].nme]} num="38" className="transitionMetals r5 c3" />
        <Element {langValue} name={Lang[Constants[39].nme]} num="39" className="transitionMetals r5 c4" />
        <Element {langValue} name={Lang[Constants[40].nme]} num="40" className="transitionMetals r5 c5" />
        <Element {langValue} name={Lang[Constants[41].nme]} num="41" className="transitionMetals r5 c6" />
        <Element {langValue} name={Lang[Constants[42].nme]} num="42" className="transitionMetals r5 c7" />
        <Element {langValue} name={Lang[Constants[43].nme]} num="43" className="transitionMetals r5 c8" />
        <Element {langValue} name={Lang[Constants[44].nme]} num="44" className="transitionMetals r5 c9" />
        <Element {langValue} name={Lang[Constants[45].nme]} num="45" className="transitionMetals r5 c10" />
        <Element {langValue} name={Lang[Constants[46].nme]} num="46" className="transitionMetals r5 c11" />
        <Element {langValue} name={Lang[Constants[47].nme]} num="47" className="transitionMetals r5 c12" />
        <Element {langValue} name={Lang[Constants[48].nme]} num="48" className="postTransitionMetals r5 c13" />
        <Element {langValue} name={Lang[Constants[49].nme]} num="49" className="postTransitionMetals r5 c14" />
        <Element {langValue} name={Lang[Constants[50].nme]} num="50" className="metalloids r5 c15" />
        <Element {langValue} name={Lang[Constants[51].nme]} num="51" className="metalloids r5 c16" />
        <Element {langValue} name={Lang[Constants[52].nme]} num="52" className="halogens r5 c17" />
        <Element {langValue} name={Lang[Constants[53].nme]} num="53" className="nobleGases r5 c18" />
      </tr>
      <tr>
        <td id="r6" class="periods unselectable r6 text-center">6</td>
        <Element {langValue} name={Lang[Constants[54].nme]} num="54" className="alkaliMetals r6 c1" />
        <Element {langValue} name={Lang[Constants[55].nme]} num="55" className="alkalineEarthMetals r6 c2" />
        <td id="star1" class="text-center">*</td>
        <Element {langValue} name={Lang[Constants[71].nme]} num="71" className="transitionMetals r6 c4" />
        <Element {langValue} name={Lang[Constants[72].nme]} num="72" className="transitionMetals r6 c5" />
        <Element {langValue} name={Lang[Constants[73].nme]} num="73" className="transitionMetals r6 c6" />
        <Element {langValue} name={Lang[Constants[74].nme]} num="74" className="transitionMetals r6 c7" />
        <Element {langValue} name={Lang[Constants[75].nme]} num="75" className="transitionMetals r6 c8" />
        <Element {langValue} name={Lang[Constants[76].nme]} num="76" className="transitionMetals r6 c9" />
        <Element {langValue} name={Lang[Constants[77].nme]} num="77" className="transitionMetals r6 c10" />
        <Element {langValue} name={Lang[Constants[78].nme]} num="78" className="transitionMetals r6 c11" />
        <Element {langValue} name={Lang[Constants[79].nme]} num="79" className="transitionMetals r6 c12" />
        <Element {langValue} name={Lang[Constants[80].nme]} num="80" className="postTransitionMetals r6 c13" />
        <Element {langValue} name={Lang[Constants[81].nme]} num="81" className="postTransitionMetals r6 c14" />
        <Element {langValue} name={Lang[Constants[82].nme]} num="82" className="postTransitionMetals r6 c15" />
        <Element {langValue} name={Lang[Constants[83].nme]} num="83" className="metalloids r6 c16" />
        <Element {langValue} name={Lang[Constants[84].nme]} num="84" className="halogens r6 c17" />
        <Element {langValue} name={Lang[Constants[85].nme]} num="85" className="nobleGases r6 c18" />
      </tr>
      <tr>
        <td id="r7" class="periods unselectable r7 text-center">7</td>
        <Element {langValue} name={Lang[Constants[86].nme]} num="86" className="alkaliMetals r7 c1" />
        <Element {langValue} name={Lang[Constants[87].nme]} num="87" className="alkalineEarthMetals r7 c2" />
        <td id="star2" class="text-center">**</td>
        <Element {langValue} name={Lang[Constants[103].nme]} num="103" className="transitionMetals r7 c4" />
        <Element {langValue} name={Lang[Constants[104].nme]} num="104" className="transitionMetals r7 c5" />
        <Element {langValue} name={Lang[Constants[105].nme]} num="105" className="transitionMetals r7 c6" />
        <Element {langValue} name={Lang[Constants[106].nme]} num="106" className="transitionMetals r7 c7" />
        <Element {langValue} name={Lang[Constants[107].nme]} num="107" className="transitionMetals r7 c8" />
        <Element {langValue} name={Lang[Constants[108].nme]} num="108" className="transitionMetals r7 c9" />
        <Element {langValue} name={Lang[Constants[109].nme]} num="109" className="transitionMetals r7 c10" />
        <Element {langValue} name={Lang[Constants[110].nme]} num="110" className="transitionMetals r7 c11" />
        <Element {langValue} name={Lang[Constants[111].nme]} num="111" className="transitionMetals r7 c12" />
        <Element {langValue} name={Lang[Constants[112].nme]} num="112" className="postTransitionMetals r7 c13" />
        <Element {langValue} name={Lang[Constants[113].nme]} num="113" className="postTransitionMetals r7 c14" />
        <Element {langValue} name={Lang[Constants[114].nme]} num="114" className="postTransitionMetals r7 c15" />
        <Element {langValue} name={Lang[Constants[115].nme]} num="115" className="postTransitionMetals r7 c16" />
        <Element {langValue} name={Lang[Constants[116].nme]} num="116" className="halogens r7 c17" />
        <Element {langValue} name={Lang[Constants[117].nme]} num="117" className="nobleGases r7 c18" />
      </tr>
      <tr>
        <td class="gap" />
      </tr>
      <tr>
        <td />
        <td colspan="2" id="lanthanidesMain" class="text-left">* {Lang.lanthanides}</td>
        <Element {langValue} name={Lang[Constants[56].nme]} num="56" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[57].nme]} num="57" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[58].nme]} num="58" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[59].nme]} num="59" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[60].nme]} num="60" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[61].nme]} num="61" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[62].nme]} num="62" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[63].nme]} num="63" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[64].nme]} num="64" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[65].nme]} num="65" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[66].nme]} num="66" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[67].nme]} num="67" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[68].nme]} num="68" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[69].nme]} num="69" className="lanthanides r6" />
        <Element {langValue} name={Lang[Constants[70].nme]} num="70" className="lanthanides r6" />
      </tr>
      <tr>
        <td />
        <td colspan="2" id="actinidesMain" class="text-left">** {Lang.actinides}</td>
        <Element {langValue} name={Lang[Constants[88].nme]} num="88" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[89].nme]} num="89" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[90].nme]} num="90" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[91].nme]} num="91" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[92].nme]} num="92" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[93].nme]} num="93" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[94].nme]} num="94" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[95].nme]} num="95" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[96].nme]} num="96" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[97].nme]} num="97" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[98].nme]} num="98" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[99].nme]} num="99" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[100].nme]} num="100" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[101].nme]} num="101" className="actinides r7" />
        <Element {langValue} name={Lang[Constants[102].nme]} num="102" className="actinides r7" />
      </tr>
      <tr>
        <td class="gap" />
      </tr>
      <tr>
        <td />
        <td colspan="18">
          <div class="flex text-center margin-bottom-20 width-100">
            <div id="alkaliMetals" class="flex-auto category alkaliMetals unselectable">{Lang.cat1}</div>
            <div id="alkalineEarthMetals" class="flex-auto category alkalineEarthMetals unselectable">{Lang.cat2}</div>
            <div id="transitionMetals" class="flex-auto category transitionMetals unselectable">{Lang.cat3}</div>
            <div id="postTransitionMetals" class="flex-auto category postTransitionMetals unselectable">{Lang.cat4}</div>
            <div id="otherNonmetals" class="flex-auto category otherNonmetals unselectable">{Lang.cat5}</div>
            <div id="metalloids" class="flex-auto category metalloids unselectable">{Lang.cat6}</div>
            <div id="halogens" class="flex-auto category halogens unselectable">{Lang.cat7}</div>
            <div id="nobleGases" class="flex-auto category nobleGases unselectable">{Lang.cat8}</div>
            <div id="lanthanides" class="flex-auto category lanthanides unselectable">{Lang.lanthanides}</div>
            <div id="actinides" class="flex-auto category actinides unselectable">{Lang.actinides}</div>
          </div>
        </td>
      </tr>
      <tr />
    </tbody>
  </table>
</div>

<Footer />
