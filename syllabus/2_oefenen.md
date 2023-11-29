# Oefenen met Processing

Deze week gaan we met elkaar kennis maken en verder oefenen met Processing. Ook is er een [opdracht](#opdracht) waarvan we het resultaat volgende week in de les gaan gebruiken (dus maak die vooral!). Voor deze week staat nog wat materiaal op het programma over variabelen, if-statements en loops. Die komen je hopelijk nog bekend voor, dus dit materiaal is vooral bedoeld als herhaling en om te zien hoe dat in Processing werkt. Aan het eind van deze week kun je geanimeerde en interactieve tekeningen maken in Processing en ben je klaar om meer structuur in je programma's aan te brengen.

## Tijdens de les

- Kennismaking
- Opfrisquiz
- [Opdracht](#opdracht) en [oefeningen](#oefeningen)

## Online materiaal

**Aanbevolen**:

- Processing tutorials, door Daniel Shiffman

  Video's op YouTube // ongeveer 1:25 tot 2:06 uur // Engels // Engelse ondertitels, vertaling mogelijk

  - [Deel 4](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6aFNOgoIMSbSYOkKNTo89uf) (t/m 4.2) over variabelen

    4.1 en 4.2 geven een goede introductie van variabelen. Het grootste verschil met Python is dat je het type van een variabele moet aangeven. Voor nu gebruiken we vooral gehele getallen, het type `int`, en kommagetallen, het type `float`.

  - [Deel 5](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6YqykuLs00261JCqnL_NNZ_) over if-statements

    Als je nog weet hoe if-statements en booleans werken uit een vorige module, kijk dan alleen [video 5.5](https://www.youtube.com/watch?v=YIKRXl3wH8Y&list=PLRqwX-V7Uu6YqykuLs00261JCqnL_NNZ_&index=5) voor een veel gebruikte toepassing van if-statements in Processing. Bekijk ook 5.1 t/m 5.4 voor een opfrisser over if-statements en booleans.

  - [Deel 6](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6bm-3M4Wntd4yYZGKwiKfrQ) over while-loops en for-loops

    De while-loop werkt hetzelfde zoals je gewend bent van andere programmeertalen, dus eventueel kun je 6.1 en 6.2 overslaan, als je dat nog weet. De for-loop in Processing werkt anders dan in Python en variabelen in loops werken ook net even anders, dus 6.3 en 6.4 zijn wel belangrijk. 6.5 en 6.6 zijn ook goed om te bekijken.

**Alternatieven**:

- Processing Examples

  Code voorbeelden // Engelse beschrijving

  - [Variables](https://processing.org/examples/variables.html) over variabelen
  - [Integers Floats](https://processing.org/examples/integersfloats.html) over het verschil tussen `int` en `float`
  - [Variable Scope](https://processing.org/examples/variablescope.html) over waar je een variabele kunt gebruiken
  - [Conditionals 1](https://processing.org/examples/conditionals1.html) over if/else-statements
  - [Conditionals 2](https://processing.org/examples/conditionals2.html) over if/else if/else-statements
  - [Iteration](https://processing.org/examples/iteration.html) over for-loops
  - [Embedding Iteration](https://processing.org/examples/embeddediteration.html) over for-loops in for-loops

  Deze voorbeelden laten de meeste dingen zien die ook in de video's uitgelegd worden. Kopieer de code en probeer wat dingen aan te passen om echt te snappen hoe het werkt!

- Programmeren in Processing, door David Fokkema

  Tekst // ongeveer 800 woorden // Nederlands

  - [Variabelen](https://davidfokkema.github.io/project-programmeren/variabelen.html) over variabelen
  - [Code herhalen (loops)](https://davidfokkema.github.io/project-programmeren/loops.html) over for-loops

## Opdracht

Deze week is er een opdracht! Je mag deze opdracht in tweetallen of alleen maken. We gaan de resultaten in de les van volgende week gebruiken, dus voor deze ene keer moet je iets inleveren. De opdracht is als volgt:

Maak een creatie, bijvoorbeeld een poppetje, een monster, een abstract figuur of wat je maar wilt! Maak het iets bijzonders. Houdt je aan de volgende voorwaarden: 

- Gebruik twee variabelen `x` en `y` in je programma die bepalen waar je creatie getekend wordt. Je mag meer variabelen gebruiken als je wilt, maar deze twee zijn verplicht.
- Zorg dat je creatie ongeveer 200 x 200 pixels groot is.
- Maak je creatie interactief, bijvoorbeeld door het te laten reageren op de positie van de muis, op muisklikken of op een toets op je toetsenbord. Maar: je mag niet de hele creatie verplaatsen! (Ogen of ledematen bewegen, kleuren veranderen, van vorm veranderen etc. zijn allemaal wel mogelijk.)
- Als je creatie een herhaald element heeft (bijvoorbeeld een gestreept shirt, of de sneeuwballen van een sneeuwpop), gebruik dan een for- of while-loop om die te tekenen.

Tip: om te controleren of je overal `x` en `y` gebruikt hebt voor de positie van je creatie, kun je aan het begin van `draw()` de regels `x = mouseX;` en `y = mouseY;` toevoegen. Je hele creatie moet dan met de muis meebewegen. (Als er een ledemaat achterblijft, dan ben je daar dus vergeten `x` en `y` te gebruiken!)

Het is handig om van te voren op papier te schetsen wat je van plan bent, zodat je kunt zien welke coördinaten je moet gebruiken. 

Als je met z'n tweeën werkt, maak dan gebruik van peer programming: een van jullie is de *driver* die de code typt, en de ander is de *navigator* die bedenkt wat er moet gebeuren. Zo kan de driver zich vooral focussen op de details en de syntax en kan de navigator nadenken over de juiste aanpak zonder na te hoeven denken over een `;`. Wissel af en toe om, zodat je wel beide vaardigheden oefent! Als je via Teams samenwerkt, kun je de ander de besturing geven bij het schermdelen, zodat diegene ook in de Processing editor kan typen.

Stuur je programma uiterlijk voor de les in week 3 naar je docent: {{ docent_email }}. Als je je creatie samen gemaakt hebt, zet dan jullie beide namen erbij.

## Oefeningen

Begin deze week met de opdracht hierboven en sla die goed op. Je creatie kun je dan ook gebruiken voor de opdrachten hieronder. (Als je het per se andersom wilt doen, kun je natuurlijk ook je bloemetje uit de oefeningen van vorige week gebruiken. Of gewoon een rechthoek, maar dat is wel saai.)

### In beweging

:::{exercise} Opstijgen
De locatie van je creatie wordt bepaald door de variabelen `x` en `y`. 

1. Laat je creatie opstijgen door een van die variabelen te veranderen in `draw`. Welke variabele bepaalt de hoogte?
2. Kun je je creatie ook schuin laten opstijgen? Hoe verander je de hoek waarmee je creatie omhoog gaat?

Maak het venster groter door de getallen in `size` aan te passen, zodat je langer van je opstijgende creatie kunt genieten voordat die het scherm verlaat!
:::

:::{exercise} Tegen het plafond
Zorg dat je creatie niet verder stijgt dan de bovenkant van het venster.

1. Welke y-coördinaat heeft de bovenkant van het venster?
2. Als je (x, y) als middelpunt van je creatie hebt gebruikt, hoe zorg je dan dat je creatie stopt voordat de bovenkant buiten het venster komt?
:::

:::{exercise} Stuitercreatie
Laat je creatie in plaats van opstijgen, nu stuiteren op de grond en tegen het plafond. Voeg hiervoor een variabele `snelheid` toe aan je programma, die aangeeft hoe snel je creatie beweegt.

1. Welke y-coördinaat heeft de onderkant van het venster? Welke Processing variabele kun je hiervoor gebruiken? (Bekijk de [Reference](https://processing.org/reference/#environment) onder Environment als je dit op wilt zoeken.)
2. Wat gebeurt er met de snelheid als je creatie de vloer of het plafond bereikt?

Als je ook natuurkunde volgt, weet je misschien dat dingen meestal niet tegen het plafond terug stuiteren maar al eerder naar beneden vallen door iets dat "zwaartekracht" heet. Kun je je creatie ook alleen op de grond laten stuiteren door de valversnelling in je programma te gebruiken? (Je hoeft niet per se 9,81 m/s{sup}`2` te gebruiken in je programma, kies een waarde die een mooi resultaat geeft!)
:::

### Creaties clonen

:::{exercise} Creaties clonen
:label: ex-creaties-clonen

Je creatie voelt zich een beetje eenzaam zo alleen in de sketch. 

1. Gebruik een while-loop om je tekening vier keer te tekenen. Waarom zie je nu nog steeds maar één creatie?

2. Pas de tekencode van je creatie aan zodat je in plaats van alleen de variabele `x`  ook de teller van je while-loop gebruikt om de locatie te bepalen.

   ```{toggle}
   Als je als teller `i` hebt gebruikt, kun je bijvoorbeeld `x` overal vervangen door `x + i`. Je moet dan wel zorgen dat je `i` met grote stappen verhoogt om genoeg ruimte te maken, bijvoorbeeld `i = i + 200`. Je kunt ook `x + (i * 200)` gebruiken in je tekencode, als je liever `i = i + 1` als teller wilt gebruiken. Zoveel mogelijkheden!
   ```

3. Kun je jouw creaties in plaats van horizontaal naast elkaar ook op een schuine lijn zetten?

4. Voeg een variabele `aantalCreaties` toe die bepaalt hoeveel creaties je tekent. Pas de afstand tussen je creaties aan op de breedte van het scherm en het aantal creaties, zodat ze over het scherm verdeeld worden.

5. Verander je programma zodat het nu een for-loop in plaats van een while-loop gebruikt. (Of andersom als je bij 1 al eigenwijs was!)

:::
