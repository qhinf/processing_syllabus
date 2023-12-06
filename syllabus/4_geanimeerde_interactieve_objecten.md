# Geanimeerde en interactieve objecten

Deze week gaan we onze objecten tot leven brengen en interactie toevoegen. Voor een deel heb je in het online materiaal van vorige week al gezien hoe je dat kunt doen, bijvoorbeeld in Shiffmans voorbeeld met de bubbels. Over interactie in een objectgeoriënteerde structuur is echter niet hel veel online materiaal te vinden, dus dat gaan we tijdens de les bespreken. Aan het eind van deze week kun je de objecten in jouw programma laten reageren op acties van de gebruiker, en dat ook nog eens op een netjes gestructureerde manier!

## Tijdens de les

We beginnen de les met een feedbackronde over je eigen project. Laat de inspiratie voor jouw project zien, vertel welke objecten er te zien zijn en welke classes je gaat definiëren of al hebt gedefiniëerd. Je medeleerlingen geven feedback op jouw keuzes. Als je niet bij de les aanwezig bent, zorg dan dat je deze feedback zelf organiseert door een of twee klasgenoten te vragen en vertel in je videopresentatie wat die feedback was en hoe je het verwerkt hebt.

De uitleg bestaat eerst uit een beetje herhaling van het online materiaal van vorige week, daarna kijken we verder naar de structuur van interacties.

- Basisprincipes van OO
- Beweging met een `update` methode
- Interactiviteit met event handlers

## Online materiaal

**Aanbevolen**:

- Processing tutorials, door Daniel Shiffman

  Video's op YouTube // ongeveer 7 minuten // Engels // Engelse ondertitels, vertaling mogelijk

  - [Video 3.3](https://www.youtube.com/watch?v=UvSjtiW-RH8&list=PLRqwX-V7Uu6by61pbhdvyEpIeymlmnXzD&index=3) over event handlers

**Alternatieven**:

- Processing tutorials, door Casey Reas en Ben Fry

  Tekst // ongeveer 1500 woorden // Engels

  - [Interactivity (vanaf Events)](https://processing.org/tutorials/interactivity#events) over event handlers

- Processing Examples

  Code voorbeelden // Engelse beschrijving

  - [Mouse Functions](https://processing.org/examples/mousefunctions.html) over event handlers

## Project

1. Welke beweging zou je in je project kunnen toevoegen? En welke interacties zou je toe willen voegen? Maak een lijstje van al je ideeën, en schroom niet om daar later nog iets aan toe te voegen.

   Probeer je niet te beperken tot wat jij denkt dat mogelijk is: sommige dingen zijn eenvoudiger te maken dan je zou denken en andere veel ingewikkelder. Daar kom je pas achter als je het probeert! En als je er niet uit komt, dan kun je altijd hulp vragen bij mij of een klasgenoot. Misschien hebben zij een idee hoe je iets simpel kan oplossen.

2. Kies een bewegend (of verkleurend, of vervormend, etc.) element uit en voeg een `update` methode toe aan die class om die beweging in actie te brengen.

3. Kies een element met interactie uit en bedenk hoe die interactie zich vertaalt naar events voor dat object. Voeg methodes voor die events toe aan je class, en roep die methodes aan in de eventmethodes in de hoofdtab van je programma.

Ga daarna verder met de rest van je project: voeg meer beweging en interactie toe aan andere objecten, of ga verder met het opfraaien van je tekeningen.

## Oefeningen

### Objecten in beweging

:::{exercise} Objecten in beweging

In {ref}`ex-creatie-opstijgen` heb je jouw creatie laten opstijgen en in {ref}`ex-creatie-class` heb je voor jouw creatie een class gemaakt met eigenschappen `x` en `y` voor de positie. In deze oefening gaan we diezelfde beweging op een nette manier in de class verwerken.

In {ref}`ex-creatie-opstijgen` heb je in de `draw` functie bijvoorbeeld een variabele `y` iedere keer een klein beetje aangepast (bijvoorbeeld `y = y - 1;`), om je creatie te laten bewegen. In de class voor jouw creatie heb je alle code die je in `draw` had geschreven om jouw creatie te tekenen in een nieuwe methode `display` gezet. Natuurlijk kunnen we daar ook die regel aan toevoegen om hetzelfde resultaat te krijgen, maar voor de structuur is het netter om in de `display` functie alleen code te zetten die jouw creatie tekent en alle andere functionaliteit in andere methodes te zetten.

1. Voeg aan je creatie een methode `update` toe, met return type `void` en geen argumenten. In deze methode maken we de aanpassingen aan de eigenschappen die je voor ieder frame maakt. Zet om je creatie te laten stijgen de regel `this.y = this.y - 1;` in die methode.

2. Als je je programma uitvoert, zal je creatie nog niet opstijgen, want de methode `update` wordt nog niet uitgevoerd. Roep deze methode ook aan in de `draw` functie, voordat je `creatie.display()` aanroept.

Nu stijgt jouw creatie ook als object!

:::

```java
// TODO
// Deze syllabus is nog in ontwikkeling. Hier komen binnenkort nog oefeningen te 
// staan. Tot die tijd kun je natuurlijk ook zelf wat doen: je hebt al verscheidene
// programma's geschreven die je kunt aanpassen! Maak bijvoorbeeld een class voor 
// je creatie en voeg daar beweging en interactie met events aan toe. Zorg dat je
// in je class geen mouseX, mouseY, mousePressed en dat soort variabelen 
// meer gebruikt!
```

### Objectgeoriënteerde interactie

:::{exercise} Beweegbare box
Bij deze oefening hoort een voorbeeldprogramma met een box die je over het scherm kunt slepen:

```java
// Sketch met een box die je met de muis over het scherm kan slepen
// Gebaseerd op https://processing.org/examples/mousefunctions.html

// Variabelen die we nodig hebben in dit programma:
// - x en y positie van de box
float boxX, boxY;
// - grootte van de box
int boxSize;
// - booleans die aangeven of
//   - de muis op dit moment over de box hangt
//   - de muis op dit moment de box vasthoudt (door te klikken)
boolean mouseOverBox, mouseLockedOnBox;
// - als de muis de box vasthoudt, op welke afstand van het midden
//   van de box de muis zit (dat moeten we weten om de box weer op 
//   de juiste plek te zetten bij het slepen)
float lockedOffsetX, lockedOffsetY;

void setup() {
  size(640, 360);
  
  // Zet de box in het midden bij de start van het programma
  boxX = width / 2;
  boxY = height / 2;
  boxSize = 75;
  
  // Initialiseer de variabelen voor het slepen
  mouseOverBox = false;
  mouseLockedOnBox = false;
  lockedOffsetX = 0.0;
  lockedOffsetY = 0.0;
  
  rectMode(RADIUS);
}

// De draw is heel simpel: we hoeven alleen de box te tekenen
// aan de hand van de variabelen die we hebben
void draw() {
  background(0);
  
  // Als de muis de box vasthoudt, maken we de box wit
  if (mouseLockedOnBox) {
    fill(#ffffff);
  // Als de muis over de box zweeft, geven we de box een witte rand
  // en tekenen we de box verder in het grijs
  } else if (mouseOverBox) {
    stroke(#ffffff);
    strokeWeight(2);
    fill(#dedede);
  // Anders tekenen we de box zonder rand en in het grijs
  } else {
    strokeWeight(0);
    fill(#dedede);
  }
  
  // Teken de box op de juiste positie
  rect(boxX, boxY, boxSize, boxSize);
}

// Hier gebeurt het echt: met deze event handlers zorgen we ervoor
// dat je de box over het scherm kunt slepen

// Deze handler wordt uitgevoerd als de muis verplaatst wordt, en 
// die kunnen we dus gebruiken om te zien of de muis nu over de box
// hangt
void mouseMoved() {
  // Als de x positie van de muis groter is dan de linkerkant van de box
  // en kleiner dan de rechterkant van de box
  if (mouseX > boxX - boxSize && mouseX < boxX + boxSize
      // en de y positie van de muis groter is dan de bovenkant van de box
      // en kleiner is dan de onderkant van de box
      && mouseY > boxY - boxSize && mouseY < boxY + boxSize) {
    // Dan is de muis op dit moment boven de box!
    mouseOverBox = true;
  } else {
    // En anders niet
    mouseOverBox = false;
  }
}

// Deze handler wordt uitgevoerd als je de linkermuisknopt indrukt, die
// gebruiken we om de box vast te pakken
void mousePressed() {
  // Als we boven de box zijn,
  if (mouseOverBox) {
    // dan kunnen we de box vastpakken
    mouseLockedOnBox = true;
    // We onthouden ook waar we de box vasthouden: als de offset 0 is,
    // dan hebben we de box precies in het midden, maar we kunnen de box
    // ook op een andere plek vastpakken. De offset is dan de afstand
    // vanaf de muis tot aan het midden.
    lockedOffsetX = mouseX - boxX;
    lockedOffsetY = mouseY - boxY;
  }
}

// Deze handler wordt uitgevoerd als we met de muis slepen, dus bewegen
// terwijl de muisknop is ingedrukt. Met deze handler bewegen we de box.
void mouseDragged() {
  // We bewegen de box alleen als we de box vasthouden bij het slepen
  // (en we dus de muisknop ingedrukt hebben terwijl we boven de box waren).
  if (mouseLockedOnBox) {
    // Dan is de nieuwe positie van de box de huidige positie van de muis,
    // gecorigeerd voor het feit dat we de box niet in het midden hoeven te
    // pakken door de offset.
    boxX = mouseX - lockedOffsetX;
    boxY = mouseY - lockedOffsetY;
  }
}

// En als laatste: als we de muis loslaten,
void mouseReleased() {
  // dan hebben we de box dus niet meer vast...
  mouseLockedOnBox = false;
}
```

In deze oefening maak je van deze Box een object, en zorg je dat de interactie via de class verloopt.

1. Lees het programma door en zorg dat je snapt hoe het werkt. Probeer eventueel wat regels aan te passen om het beter te begrijpen.

2. Verplaats alle variabelen naar een class Box, maak een `display` methode om de box te tekenen.

3. Maak ook een methode `boolean isOver(float posX, float posY)` die `true` returnt als `posX` en `posY` binnen de box vallen (en anders `false` returnt). Deze methode kun je dan in je event handlers gebruiken.

4. In main zijn vier eventmethodes: mouseMoved, mousePressed, mouseDragged en mouseReleased. Wat gebeurt er in die functies? Welke events zijn dat vanuit het perspectief van de box? Maak methodes in de class Box voor deze events.

   Bijvoorbeeld: als mousePressed gebeurd op het moment dat de muis over die box is, dan kun je dat zien als een `locked` event voor de box.

5. Roep deze eventmethodes aan vanuit de eventmethodes in de hoofdtab, als er door dat event iets verandert voor de box. In mousePressed roep je bijvoorbeeld alleen de methode voor het `locked` event aan, als de muis op dat moment boven de box zweeft (gebruik hier de `isOver` methode!)

Als alles goed is gegaan, kun je nu de box weer over het scherm slepen!
:::

:::{exercise} Meerdere beweegbare boxes
Het mooie van objectgeoriënteerd programmeren is dat je relatief makkelijk meerdere objecten van dezelfde class kunt maken.

1. Voeg een tweede object van class Box toe aan je programma. Pas elke eventmethode aan om de events ook door te geven naar je tweede box, als een event voor die box van toepassing is.

Je hebt nu best veel gekopieerde code in je programma... Volgende week gaan we zien hoe je dit beter op kunt lossen door gebruik te maken van lijsten, zodat je zoveel boxes in je programma kunt zetten als je maar wilt, zonder extra code te hoeven schrijven!
:::
