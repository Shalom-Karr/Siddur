# Offline HTML Siddur - סידור

A single-file, offline Hebrew siddur that runs in any browser. No JavaScript, no network
requests, no dependencies — the fonts and the full text are embedded directly in the HTML,
so it works on kosher phones, dumbphones, and anything else with a browser.
 
## Credits and origin
 
This is an adaptation. It is not original work, and the people below did the part that
actually matters — digitizing, typesetting, and assembling the text.
 
**Original siddur — קנאפער ידען (Knaper Yidden) on iVelt**
The underlying siddur was built and posted on the iVelt forum.
<https://www.ivelt.com/forum/memberlist.php?mode=viewprofile&u=5372>
 
**Dumbphone HTML version — "Sams Club" on JTech Forums**
Repackaged as a self-contained HTML file for MindPhone and other kosher phones, and shared
in the thread *Complete Siddur HTML for Dumbphones*.
<https://forums.jtechforums.org/t/complete-siddur-html-for-dumbphones/8343>
 
Everything here is derived from those two. Any bugs in this version are mine, not theirs.
 
### Additional credits
 
- One of the source builds credits its Hebrew text to **the Metsudah Siddur via Sefaria**
  (CC-BY) and uses **Noto Serif Hebrew** (SIL Open Font License).
- One of the source builds carries the Yiddish credit line
  *אהערגעשטעלט דורך ׳שוואכע מעשיות - אייוועלט׳* and is dedicated
  *לע״נ מרן רבינו יואל ב״ר חנני׳ יום טוב זצוקללה״ה*. That dedication is preserved.
## What's included
 
Weekday Shacharis, Mincha, Maariv and Maariv for Motzei Shabbos; Sefiras HaOmer; Kiddush
Levana; Krias Shema al HaMitah; birchos hanehenin, bracha achrona and assorted brachos;
Tefillas HaDerech; Birkas HaMazon; Eruv Tavshilin; Netilas Lulav; Rosh Chodesh; Shalosh
Regalim; Nissan; the Haggadah; Shir HaShirim; Sukkos; Simchas Torah; Shavuos; Yotzros;
Chanukah; Purim; taaniyos and aveilus; seder hakrios; Birkas Kohanim; Tikkun Chatzos;
Tikkun HaKlali; and the full Tehillim.
 
## Features
 
- Fully vowelized text throughout
- Section jump menu in the top bar of every service
- Light / dark / auto theme
- Three text sizes and three line-spacing settings
- Multiple font choices
- Works completely offline — save the file and open it
## Usage
 
Save the `.html` file to the device and open it in the browser. That's the whole install.
It can also be hosted on any static web server or served from a local file path.
 
## Font licensing — read before redistributing
 
Some builds embed **Times New Roman** (Monotype) and **SF Hebrew** (Apple) as base64 data
URIs. Neither license permits redistributing the font files, which is exactly what
base64-embedding does. Before sharing this publicly, replace them with open alternatives:
 
- Noto Serif Hebrew (SIL OFL)
- Frank Ruehl CLM (GPL with font exception)
- Taamey D / Taamey Frank CLM (SIL OFL)
This also cuts a large chunk off the file size — the embedded fonts alone account for
roughly 550 KB.
 
## Text attribution
 
If the Hebrew text originates from Sefaria, the CC-BY license requires attribution in the
distributed file itself, not only in this README. Make sure the credit line stays in the
HTML.
 

