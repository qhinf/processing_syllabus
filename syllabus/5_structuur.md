# Structuur in een Processing sketch

Je hebt inmiddels al wat ervaring met het opdelen van een programma in verschillende objecten, maar we kunnen nog wel wat meer structuur aanbrengen, bijvoorbeeld door objecten in objecten te zetten of een object verder uit te splitsen. Als je meer objecten in je programma hebt, kan het ook lastiger worden om die objecten netjes met elkaar te laten reageren, bijvoorbeeld als je wilt dat twee ballen tegen elkaar aan botsen. Daar gaan we dus ook naar kijken. Het online materiaal hierover gaat er niet heel diep op in, dus in de les besteden we er ook aandacht aan. 

Het komt ook vaak voor dat je heel veel objecten van dezelfde class in je programma wilt gebruiken. In dat geval is een lijst of array het aangewezen middel. Hierover kun je online wel een heleboel vinden.

Aan het eind van deze week kun je je programma dus nog beter structureren, maar er ook voor zorgen dat de verder opgesplitste onderdelen nog wel op elkaar kunnen reageren.

## Tijdens de les

- Objecten in objecten, volgens de principes van objectgeoriënteerd programmeren
- Interactie en communicatie tussen objecten

## Online materiaal

**Aanbevolen**:

- Processing tutorials, door Daniel Shiffman

  Video's op YouTube // ongeveer 1:05 uur // Engels // Engelse ondertitels, vertaling mogelijk

  - [Deel 8 (vanaf 8.5)](https://www.youtube.com/watch?v=V7k5bFQbhG0&list=PLRqwX-V7Uu6bb7z2IJaTlzwzIg_5yvL4i&index=5) over objecten in objecten en over interactie tussen objecten
  - [Deel 9](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6bO9RKxHObluh-aPgrrvb4a) over lijsten

**Alternatieven**:

- Processing tutorials, door Casey Reas en Ben Fry

  Tekst // ongeveer 3400 woorden // Engels

  - [Arrays](https://processing.org/tutorials/arrays) (t/m Array of Objects) over lijsten

- Processing Examples

  Code voorbeelden // Engelse beschrijving

  - [Composite Objects](https://processing.org/examples/compositeobjects.html) over objecten in objecten
  - [Bouncy Bubbels](https://processing.org/examples/bouncybubbles.html) over interactie tussen objecten
  - [Array Objects](https://processing.org/examples/arrayobjects.html) over een lijsten met objecten

## Project

1. Bekijk de structuur van je project. Zijn er classes die beter binnen een andere class zouden passen? Zijn er grote classes die je misschien kunt opsplitsen in een aantal kleinere classes? Vanaf nu is het een goed idee om jezelf deze vragen elke week te stellen! En als je deze vragen hebt beantwoord, is het natuurlijk tijd om de structuur van je project te verbeteren!
2. Welke interactie zou je tussen objecten willen hebben? Zijn er bijvoorbeeld objecten die tegen elkaar aan kunnen botsen? Of een bliksemflits die een boom in brand zet? Maak een lijstje van interacties die je toe kunt voegen, en begin die te programmeren in je project.

## Oefeningen

### Objecten in objecten

```java
// TODO
// Deze syllabus is nog in ontwikkeling. Hier komen binnenkort nog oefeningen te 
// staan. Tot die tijd kun je natuurlijk ook zelf wat doen: je hebt al verscheidene
// programma's geschreven die je kunt aanpassen! Splits bijvoorbeeld je creatie uit 
// in kleinere classes. Misschien is `Oog` een nuttige klas om uit te splitsen?
```

### Interactie tussen objecten

```java
// TODO
// Deze syllabus is nog in ontwikkeling. Hier komen binnenkort nog oefeningen te 
// staan. Tot die tijd kun je natuurlijk ook zelf wat doen: je hebt al verscheidene
// programma's geschreven die je kunt aanpassen! Voeg bijvoorbeel een interactie toe
// tussen je creaties: laat ze tegen elkaar aan stuiteren of laat de kleur van de één
// afhangen van de positie van de ander. Verzin iets leuks!
```

### Veel meer objecten

:::{exercise} Creaties vaker clonen

In {ref}`ex-creatie-class-clonen` heb je twee kopieën van je creatie gemaakt met een tweede variabele. Die code was al aanzienlijk duidelijker dan de loops in {ref}`ex-creaties-clonen`, maar om een kudde van 100 creaties te tekenen heb je dan natuurlijk heel veel variabelen nodig. In deze oefening maken we een lijst om creaties in op te slaan.

1. Maak een nieuwe variabele bovenaan je programma (in de hoofdtab) voor het aantal creaties dat je gaat maken.

   ```java
   int aantalCreaties = 5;
   ```

2. Vervang de variabele `Creatie creatie;` door een variabele met een lijst van creaties. Maak ook meteen die lijst met de juiste hoeveelheid elementen:

   ```java
   Creatie[] creaties = new Creatie[aantalCreaties];
   ```

   Je kunt specifieke creaties in deze lijst nu benaderen met `creaties[index]`, waarbij `index` een getal van 0 tot (en niet t/m!) `aantalCreaties` is.

3. In `setup` moet je nu, in plaats van één nieuwe creatie, `aantalCreaties` nieuwe creaties maken. Gebruik daarvoor een for-loop en laat de positie van je creatie afhangen van de teller in die loop:

   ```java
   for (int i = 0; i < aantalCreaties; i++) {
     creaties[i] = new Creatie(100 + i * 200, 500);
   }
   ```

4. Tot slot moet je ook al deze creaties tekenen. Pas daarvoor de code in `draw` aan met een for-loop en roep de `display` methode van iedere creatie in de lijst aan:

   ```java
   for (int i = 0; i < aantalCreaties; i++) {
     creaties[i].display();
   }
   ```

Je kunt nu heel makkelijk het aantal creaties in je programma wijzigen, door alleen een ander getal bij `aantalCreaties` in te vullen en eventueel de posities in `setup` aan te passen. Probeer ook om de posities af te laten hangen van `width`, `height` en `aantalCreaties`, zodat de creaties altijd over het scherm verspreid worden, hoeveel het er ook zijn en hoe groot het venster ook is.

:::

:::{exercise} Heel veel beweegbare boxes

In {ref}`ex-meerdere-beweegbare-boxes` heb je twee beweegbare boxes gemaakt. Pas dat programma aan met een nieuwe variabele `aantalBoxes` en een lijst waarin je de Box objecten bewaart. Gebruik in de event handlers een for-loop om events aan alle boxes door te geven waarop dat event van toepassing is.

:::
