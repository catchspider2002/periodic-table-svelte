<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import Constants from "../../components/constants.js";
  import { onMount } from "svelte";
  import lang from "./locale.js";

  let List;

  onMount(async () => {
    const module = await import("list.js");
    List = module.default;

    var options = {
      valueNames: ["listName", "listNum", "listSym"],
    };

    var userList = new List("mainList", options);
  });

  let langValue = Lang.lang;

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
      <div id="mainList">
        <div class="flex flex-wrap">
          <div class="m-b-30 flex-auto m-x-15"><input class="search" id="searchText" aria-label="Search" /></div>
          <div class="m-b-30 flex-auto m-x-15">
            <button id="buttonSortNum" class="sort" data-sort="listNum"> <span> {Lang.sortNumber} </span> <span id="sortNum" /></button>
          </div>
          <div class="m-b-30 flex-auto m-x-15">
            <button id="buttonSortName" class="sort" data-sort="listName"> <span> {Lang.sortName} </span> <span id="sortNm" /></button>
          </div>
          <div class="m-b-30 flex-auto m-x-15">
            <button id="buttonSortSym" class="sort" data-sort="listSym"> <span> {Lang.sortSymbolr} </span> <span id="sortSym" /></button>
          </div>
        </div>
        <div class="list text-center listGrid m-x-15">
          {#each Constants as ele}
            <a class="elementList" href="{langValue}/{ele.nme}">
              <div class="list-content flex">
                <div class="listSym heavyFont">{ele.sym}</div>
                <div class="listName">{Lang[ele.nme]}</div>
                <div class="listNum heavyFont"><span>{getNum(ele.num)}</span></div>
              </div>
            </a>
          {/each}
        </div>
      </div>
    </div>
  </div>
</div>

<div class="footer">
  <Footer />
</div>
