# Terningkast - Middels

## Hva skal skje? @showdialog
Vi skal
- vise tallene 1 til 6 når vi starter, etterfulgt av en terning uten øyne
- sørge for at man bare får kastet en gang
- trekke et tilfeldig tall mellom 1 og 6 og få det til å blinke fem ganger
- starte et nytt kast

## Vise tallene 1 til 6 - Steg 1
I ``||basic:ved start||`` skal du sette inn ``||loops:gjenta for||`` ``||variables:indeks||`` ``||loops:fra 0 til 4||``.

Den finner du i ``||loops:Løkker||``.

``` blocks
for (let indeks = 0; indeks <= 4; indeks++) {}
```

## Steg 2
Den blokken du nettopp satt inn teller fra 0 til 4, altså 0, 1, 2, 3, 4. Det er fem tall.

Vi skal ha seks tall, så endre ``4``-tallet til ``5``.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {}
```

## Steg 3
Vi skal vise tallene. Sett inn ``||basic:vis tall||`` og ``||basic:pause (ms) 100||``.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(0)
    basic.pause(100)
}
```

## Steg 4 @showhint
Hvis du bytter ut ``0`` med ``||variables:indeks||`` vil den telle 0, 1, 2, 3, 4, 5. Men vi vil telle tallene 1, 2, 3, 4, 5, 6.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(0)
    basic.pause(100)
}
```

### Steg 4a
Gå inn på ``||math:Matematikk||`` og finn ``0 + 0``. Dette skal stå i stedet for ``0`` i ``||basic:vis tall||``.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(0 + 0)
    basic.pause(100)
}
```

### Steg 4b
Dra ``||variables:indeks||`` fra ``||loops:gjenta||``-blokken ned til den ene ``0``-tallet.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 0)
    basic.pause(100)
}
```

### Steg 4c
Bytt ut det andre ``0``-tallet med ``1``.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
    basic.pause(100)
}
```

## Steg 5
Vi vil at tallet skal vises litt lenger enn 100 millisekunder, så bytt ut ``100`` med ``500``.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
    basic.pause(500)
}
```

## Steg 6
Nå vil vi se en terning uten øyne. Under ``||loops:gjenta||``-blokken setter du inn ``||basic:vis skjerm||`` og tegner en terning uten øyne.

``` blocks
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
    basic.pause(500)
}
basic.showLeds(`
    # # # # #
    # . . . #
    # . . . #
    # . . . #
    # # # # #
    `)
```

## Sørge for at man bare kan kaste 1 gang - Steg 1
Lag en ``||variables:Variabel||`` som du kaller ``Kast``.

Øverst i ``||basic:ved start||``, over ``||loops:gjenta||``-blokken, setter du inn at ``Kast`` er ``0``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
    basic.pause(500)
}
```

## Trekke et tall og få det til å blinke - Steg 1
Når vi trykker på ``||input:knapp A||`` skal vi kaste terning. Sett inn ``||input:når knapp A trykkes||``.

``` blocks
input.onButtonPressed(Button.A, function(){})
```

## Kast-variabel @showdialog
``||variables:Kast||`` skal være enten ``0`` eller ``1``. Vi har satt at den er ``0`` ved start.

Hvis ``||variables:Kast||`` er
- ``0``: Du har ikke kastet ennå
- ``1``: Du har kastet

## Steg 2a
Hvis ``||variables:Kast||`` er ``0`` så kan vi kaste. Vi setter inn en ``||logic:hvis||``-blokk og sjekker om ``||variables:Kast||`` er ``0``.

Trykk på ``||logic:Logikk||`` og sett inn ``||logic:hvis sann så||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (true) {
    
    }
})
```

### Steg 2b
Gå tilbake til ``||logic:Logikk||``, finn ``||logic:0 = 0||`` og sett den inn i stedet for ``sann``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (0 == 0) {
    
    }
})
```

### Steg 2c
Bytt ut første ``0`` med ``||variables:Kast||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
    
    }
})
```

## Steg 3
Nå har vi kastet. Da ender vi ``||variables:Kast||`` med ``1``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
    }
})
```

## Steg 4a
Lag en ny variabel som heter ``Tilfeldig``. Dette skal være det tilfeldige tallet.
Sett inn ``||variables:sett Tilfeldig til 0||``, og bytt ut ``0`` til et tilfeldig tall mellom 1 og 6.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = 0
    }
})
```

### Steg 4b
Bytt ut ``0`` med ``||math:velg tilfeldig 1 og 10||``. Den finner du under ``||math:Matematikk||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(0, 10)
    }
})
```

### Steg 4c
Bytt ut ``0`` og ``10`` med ``1`` og ``6``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
    }
})
```

## Steg 5a
Nå skal tallet blinke. Fra ``||loops:Løkker||`` setter du inn ``||loops:gjenta 4 ganger||``.
Siden vi skal få den til å blinke fem ganger må ``4`` byttes ut med ``5``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 4; index++) {}
    }
})
```

### Steg 5b
Bytt ut ``4`` med ``5``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {}
    }
})
```

## Steg 6
Inni ``||loops:gjenta||``-blokken setter du inn ``||basic:tøm skjerm||`` og ``||basic:pause (ms) 100||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(100)
        }
    }
})
```

## Steg 7a
Nå skal vi vise det tilfeldige tallet. Sett inn ``||basic:vis tall||`` ``||variables:Tilfeldig||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(100)
            basic.showNumber(0)
        }
    }
})
```

### Steg 7b
Bytt ut ``0`` til ``||variables:Tilfeldig||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(100)
            basic.showNumber(Tilfeldig)
        }
    }
})
```

## Steg 8
Avslutt med å sette inn en ny pause på 100 millisekunder.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Kast += 1
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(100)
            basic.showNumber(Tilfeldig)
            basic.pause(100)
        }
    }
})
```

## Nytt kast - Steg 1
Når vi trykker på ``||input:knapp A+B||`` kan vi kaste på nytt. Sett inn blokken ``||input:når knapp A+B trykkes||``.

``` blocks
input.onButtonPressed(Button.AB, function(){

})
```

## Steg 2
``||variables:Kast||`` er ``1``, som betyr at vi har kastet alt. Vi må endre denne tilbake til ``0``.

``` blocks
input.onButtonPressed(Button.AB, function(){
    Kast = 0
})
```

## Steg 3
Vi skal helt til slutt vise terning uten øyne, som vi har gjort på starten.

``` blocks
input.onButtonPressed(Button.AB, function(){
    Kast = 0
    basic.showLeds(`
        # # # # #
        # . . . #
        # . . . #
        # . . . #
        # # # # #
        `)
})
```
