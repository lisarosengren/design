---
Title: Load
Description: This is my load analysis.
Template: analysis
---

Webbplatsers laddningstid och användbarhet
=======================

Uppgiften går ut på att mäta tre olika webbplatsers laddningstid och se om det finns saker som kan förbättras.

Urval
-----------------------

Jag har valt att undersöka webbplatser tillhörande Blekinge Tekniska Högskola (bth.se), Malmö stad (malmo.se) samt Svenska Spel Tur (svenskaspel.se/tur). Det är samma urval som i förra rapporten och jag är nyfiken på hur de presterar.

Metod
-----------------------

Jag har använt Firefox Developer Tools och fliken "Network" för att mäta laddningstid. För att inte webbläsaren ska använda cache så har jag tryckt på shift-ctrl-r och laddat om sidorna. Mätningen har gjorts tre gånger och medelvärdet har räknats ut. Sidorna har även kontrollerats med Google PageSpeed insights (https://developers.google.com/speed/pagespeed/insights/) som sätter betyg och tipsar om prestandaoptimering. 

Resultat
-----------------------
<div class="embed-container">
<iframe class="sheet" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vT26UJqsEvxhI0muyjkPmXXFqIv7IBmOC7EHgeUTU0dEVFQGJ8Cq2zy5qu0glpmcqwMVYFyxdMI8LF1/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>
</div>

LCP - Largest Conentful Paint, sekunder <br>
INP - Interaction to Next Paint, millisekunder<br>
CLS - Cumulative Layout Shift<br>
FCP - First Contentful Paint, sekunder<br>
TTFB - Time to First Byte, sekunder<br>
Laddningstid - sekunder<br>


BTH 1: [Förstasidan](https://www.bth.se/)<br>
BTH 2: [Program och kurser](https://www.bth.se/utbildning/program-och-kurser/)<br>
BTH 3: [Studentstöd](https://www.bth.se/bli-student/studentstod/)<br>
Malmö stad 1: [Förstasidan](https://malmo.se/)<br>
Malmö stad 2: [Kontakta oss](https://malmo.se/Kontakta-Malmo-stad.html)<br>
Malmö stad 3: [Så växer Malmö](https://malmo.se/Stadsutveckling.html)<br>
Svenska Spel Tur 1: [Förstasidan](https://www.svenskaspel.se/tur)<br>
Svenska Spel Tur 2: [Kundservice](https://www.svenskaspel.se/kundervice)<br>
Svenska Spel Tur 3: [Ge bort Triss](https://www.svenskaspel.se/triss/ge-bort)

#### BTH
![BTH snapshot](../image/bth.png)
BTH får en del gula och röda betyg. PageSpeed Insights har åsikter som storleken på DOM-trädet och JavaScript som blockerar renderingen och JavaScript som inte används.  

#### Malmö Stad
![Malmö Stad snapshot](../image/malmo.png)
Malmö Stad håller sig nästan bara till grönt. Sidan som sticker ut är "Så växer Malmö". Den tar längre tid på sig i DevTools och är betydligt större än de andra, vilket beror på bilderna. För förstasidan är det främst JavaScript som tar plats, på "Så växer Malmö" är det bilderna. Så det främsta tipset här är att se över bildernas storlek.

#### Svenska Spel Tur
![Svenska Spel Tur snapshot](../image/svenskaspeltur.png)

Svenska Spel Tur laddar markant fler resurser än de övriga, men är inte väldigt mycket större. Tar dock längre tid på sig i DevTools. Det är några röda betyg från PageSpeed Insights. Många bilder, men det är JavaScript som tar mest plats. Även här verkar det blockera renderingen.


Analys
-----------------------
Det är mestadels grönt i PageSpeed Insights, den som spretar lite där är BTH. Svenska Spel Tur sticker ut med sina resurser och tiden det tar att ladda. Malmö har, med ett undantag, de absolut minsta och snabbaste sidorna. Vid första anblicken av tabellen är det lätt att tänka att BTH hamnar sist i rangordningen, men jag väljer att Placera Svenska Spel där. Baserat på laddningstiden från DevTools. Därmed kommer BTH på andraplats. Malmö är en vinnare i det här testet.

De vanligaste förbättringsåtgärderna verkar vara att se över JavaScript. Dels storlek och dels att scripten stoppar upp laddningen av övrigt innehåll. DOM-träden verkar också vara ett bekymmer. Åtgärdsförslag för bilder förekom i mindre utsträckning än jag hade trott.

Generellt så uppfattar jag sidorna som jag har valt som rätt långsamma när jag ska ladda dem. Men det kan nog till stor del skyllas på min egen internetförbindelse. Gränsen för när jag tycker det är segt verkar vara runt 2 sekunder. Det klarar två av Malmös sidor i DevTools. De andra gick över tiden. Malmö klarar LCP under 2 sekunder på samtliga sidor när man mäter i PageSpeed Insight. BTH klarar 2 av 3 medan Svenska Spel bara klarar sig i 1 av fallen.      

Referenser
-----------------------
[Google PageSpeed insights](https://developers.google.com/speed/pagespeed/insights/)


Övrigt
-----------------------
Lisa Rosengren