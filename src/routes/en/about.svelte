<script>
  import Lang from "./locale.js";
  // import Footer from "./_Footer.svelte";
  // import Nav from "./_Nav.svelte";

  function id(text) {
    return document.getElementById(text);
  }
</script>

<!-- <Nav /> -->

<div class="content-wrapper">
  <div class="container">
    <div id="about" class="row text-upper aboutHeader text-center heavyFont">{Lang.about}</div>
    <div>
      <span>{Lang.line1}</span>
      <span>{Lang.line2}</span>
      <ul id="features">
        <li>{Lang.feature1}</li>
        <li>{Lang.feature2}</li>
        <li>{Lang.feature3}</li>
        <li>{Lang.feature4}</li>
        <li>{Lang.feature5}</li>
        <li>{Lang.feature6}</li>
        <li>{Lang.feature7}</li>
        <li>{Lang.feature9}</li>
      </ul>
      <span class="heavyFont">{Lang.contact}</span>: <a
        class="underlineLink"
        href="mailto:naveen@periodic-table.io?subject=Periodic-Table.io">naveen@periodic-table.io</a>
      <br />
      <span class="heavyFont">Github</span>: <a
        class="underlineLink"
        href="https://github.com/catchspider2002/periodic-table.io">https://github.com/catchspider2002/periodic-table.io</a>
    </div>
    <div class="row text-upper aboutHeader text-center heavyFont">{Lang.changelog}</div>
    <div>
      <ul id="logs">
        <li class="font-weight-600 versionHeader margin-top-30">October 9, 2020</li>
        <li>Added Armenian translation</li>
        <li>Updated Croatian translation</li>
        <li class="font-weight-600 versionHeader margin-top-30">October 5, 2020</li>
        <li>Added a new printable - Flash Cards in <a class="underlineLink" href="printables.html"><span>Printables</span></a> page</li>
        <li>Added Malay translation</li>
        <li>Updated Greek, Hebrew, Hindi, Norwegian Bokmal, Polish, Romanian, Vietnamese and Dutch translations</li>
        <li>Fixed the top navbar so that the navbar does not overlap the scrollbard</li>
        <li class="font-weight-600 versionHeader margin-top-30">August 2020</li>
        <li>Updated the icons in the navbar to outline icons</li>
        <li>Simplified localisation and individual languages will now be included in the url</li>
        <li>Added a new printable in <a class="underlineLink" href="printables.html"><span>Printables</span></a> page</li>
        <li>Added CAS Number and PubChem CID Number</li>
        <li>Fixed electron configuration rendering issues in Edge and Chrome</li>
        <li>Updated Arabic, Persian, Hindi, Italian, Indonesian, Vietnamese, German, Greek, Polish, Dutch, Slovak, Chinese (Simplified) and Chinese (Traditional) translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">July 2020</li>
        <li>Added a new printable in <a class="underlineLink" href="printables.html"><span>Printables</span></a> page</li>
        <li>
          Added a new page - <a class="underlineLink" href="translation.html"><span>Translation</span></a> where you can check the status of each language
          and contribute translations
        </li>
        <li>Added mass number, number of protons, electrons and neutrons</li>
        <li>The line height for the Elements page is increased and the text is easily readable</li>
        <li>Updated Polish, Croatian, Chinese Simplified, Croatian and Korean translation</li>
        <li>Added an option in Settings to change the style of the periodic table from 3 options</li>
        <li>Replaced the dropdown for temperature in Settings with a radio select</li>
        <li>Updated the navbar header from a gradient to solid color which now matches with the window color when opened as PWA</li>
        <li class="font-weight-600 versionHeader margin-top-30">June 2020</li>
        <li>Modified the style of the element page to use more shadows and less color</li>
        <li>Modified the colors of the Settings popup for both light and dark themes</li>
        <li>Added Instagram page link to the footer</li>
        <li>Added a new printable in <a class="underlineLink" href="printables.html"><span>Printables</span></a> page</li>
        <li>
          Added <a
            class="underlineLink"
            target="_blank"
            href="https://feedback.periodic-table.io/"
            rel="noopener noreferrer"><span>Suggestions</span></a> where new suggestions or feature requests can be provided
        </li>
        <li>Fonts for Thai and Hebrew are updated</li>
        <li>Reduced extra spacing on top and bottom sides of the electronic configuration</li>
        <li>Updated Chinese Simplified, Croatian, Portuguese and Danish translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">May 2020</li>
        <li>Updated Polish, Russian, Vietnamese, Slovenian, Chinese Simplified translations</li>
        <li>
          Added a new page - <a class="underlineLink" href="printables.html"><span>Printables</span></a> which provides a printable version of the periodic
          table which will be updated regularly
        </li>
        <li>
          Added a new page - <a class="underlineLink" href="credits.html"><span>Credits</span></a> for translations which was earlier appearing in About
          page
        </li>
        <li>Added icons to the navigation bar at the top</li>
        <li>Added footer component on all pages which includes quick links not available in the top navigation bar</li>
        <li>Updated link colors to match the theme color</li>
        <li>Reduced the number of colors in Settings from 25 to 10 which matches with the periodic table colors</li>
        <li>Fixed the layout bug where the 2nd and 3rd row were appearing with a huge space on iOS devices</li>
        <li>Fixed scrollbar styles for all browsers</li>
        <li>Added an open-source license on Github</li>
        <li>Removed theme switching to enable light or dark mode from Settings and a dedicated button is available in the top navigation bar</li>
        <li>Replaced the existing static image of electronic configuration with an animated version</li>
        <li>Please contact me at naveen@periodic-table.io if you have any suggestions or issues with the website</li>
        <li class="font-weight-600 versionHeader margin-top-30">Feb 2020</li>
        <li>Modified colors at the navigation bar for better accessibility</li>
        <li>
          Updated Persian, Croatian, Hungarian, Polish, Greek, Hebrew, Portuguese, German, Spanish, Chinese (Traditional), Russian, Thai, French,
          Italian, Chinese (Simplified) and Turkish translations
        </li>
        <li class="font-weight-600 versionHeader margin-top-30">May 2019</li>
        <li>Added Store page for t-shirts and other merchandise</li>
        <li>Added English (UK) translation</li>
        <li>Updated Chinese (Simplified), Portuguese, Spanish, Indonesian, Vietnamese and Chinese (Traditional) translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">Apr 2019</li>
        <li>Updated Arabic, Italian and Croatian translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">Dec 2018</li>
        <li>Added Slovenian, Norwegian (Nynorsk) and Croatian translations</li>
        <li>Updated Danish, Japanese and Italian translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">Nov 2018</li>
        <li>Added Danish, Greek, Thai and Hebrew translations</li>
        <li>Updated Arabic, Chinese (Traditional), Chinese (Simplified), Portuguese, Catalan, German and Japanese translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">Jun 2018</li>
        <li>Updated Russian, French and Arabic translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">May 2018</li>
        <li>Updated Persian, Czech, Italian, Dutch, Catalan, Vietnamese, Hungarian, Indonesian and Japanese translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">Apr 2018</li>
        <li>Updated Dutch and Korean translations</li>
        <li class="font-weight-600 versionHeader margin-top-30">Mar 2018</li>
        <li>Released the first version of the website with Progressive Web App (PWA) features</li>
        <li>Updated the colors of the periodic table</li>
        <li>Added options for wide and large tiles when website is pinned to Start on Windows 10</li>
        <li>Added Hindi, Chinese (Traditional), Arabic, Polish and Swedish translations</li>
        <li>Updated Japanese and Dutch translations</li>
      </ul>
    </div>
    <div class="row text-upper aboutHeader text-center heavyFont">{Lang.languages}</div>
    <div>
      <div class="pb-8">
        {Lang.enTrans}; {Lang.arTrans}; {Lang.bgTrans}; {Lang.caTrans}; {Lang.csTrans}; {Lang.daTrans}; {Lang.deTrans}; {Lang.elTrans}; {Lang.esTrans};
        {Lang.faTrans}; {Lang.fiTrans}; {Lang.frTrans}; {Lang.heTrans}; {Lang.hiTrans}; {Lang.hrTrans}; {Lang.huTrans}; {Lang.idTrans}; {Lang.itTrans};
        {Lang.jaTrans}; {Lang.koTrans}; {Lang.msTrans}; {Lang.nlTrans}; {Lang.nnTrans}; {Lang.plTrans}; {Lang.ptTrans}; {Lang.roTrans}; {Lang.ruTrans};
        {Lang.skTrans}; {Lang.slTrans}; {Lang.srTrans}; {Lang.svTrans}; {Lang.thTrans}; {Lang.trTrans}; {Lang.ukTrans}; {Lang.viTrans}; {Lang.zhTrans};
        {Lang.chTrans};
      </div>
    </div>
  </div>
</div>

<!-- <Footer /> -->
