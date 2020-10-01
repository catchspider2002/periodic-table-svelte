<script>
  import Lang from "./locale.js";
  import Footer from "./_Footer.svelte";
  import Nav from "./_Nav.svelte";
  import Constants from "../../components/constants.js";
  import { onMount } from "svelte";

  let List;

  onMount(async () => {
    const module = await import("list.js");
    List = module.default;

    var options = {
      valueNames: ["listName", "listNum", "listSym"],
    };

    var userList = new List("mainList", options);
  });
  function id(text) {
    return document.getElementById(text);
  }

  function sortFunc(var1, var2, var3) {
    var sortUp = "&nbsp;↑";
    var sortDown = "&nbsp;↓";

    id(var1).innerHTML = id(var1).innerHTML === sortUp ? sortDown : sortUp;
    id(var2).innerHTML = "";
    id(var3).innerHTML = "";
  }

  let sortByNumber = () => {
    sortFunc("sortNum", "sortNm", "sortSym");
  };

  let sortByName = () => {
    sortFunc("sortNm", "sortNum", "sortSym");
  };

  let sortBySymbol = () => {
    sortFunc("sortSym", "sortNm", "sortNum");
  };

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

<Nav />

<div class="content-wrapper">
  <div class="container">
    <div class="row">
      <div id="mainList">
        <div class="flex flex-wrap">
          <div class="m-b-30 flex-auto m-x-15"><input class="search" id="searchText" aria-label="Search" /></div>
          <div class="m-b-30 flex-auto m-x-15">
            <button class="sort" data-sort="listNum" on:click={sortByNumber}><span> {Lang.sortNumber}</span><span id="sortNum" /></button>
          </div>
          <div class="m-b-30 flex-auto m-x-15">
            <button class="sort" data-sort="listName" on:click={sortByName}><span> {Lang.sortName}</span><span id="sortNm" /></button>
          </div>
          <div class="m-b-30 flex-auto m-x-15">
            <button class="sort" data-sort="listSym" on:click={sortBySymbol}><span> {Lang.sortSymbol}</span><span id="sortSym" /></button>
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

<Footer />
