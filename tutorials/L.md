# Terningkast - Lett

## Steg 1
Vi begynner med å lage en terning uten øyne ``||basic:ved start||``.

``` blocks
basic.showLeds(`
    # # # # #
    # . . . #
    # . . . #
    # . . . #
    # # # # #
    `)
```

## Hva skal vi lage? @showdialog
Når vi kaster terning får vi et tilfeldig tall mellom 1 og 6. Vi skal trekke et tilfeldig tall og få det til å blinke fem ganger.

## Steg 2
Begynn med å sette inn ``||input:Når knapp A trykkes||``.

``` blocks
input.onButtonPressed(Button.A, function(){})
```

## Steg 3
Lag en ``||variables:variabel||`` og kall den ``Tilfeldig``.

Inni ``||input:knapp A||``-blokken setter du inn ``||variables:sett Tilfeldig til 0||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = 0
})
```

## Steg 4
``Tilfeldig`` skal ikke være 0. Den skal være vårt tilfeldige tall.

Trykk på ``||math:Matematikk||`` og sett inn ``||math:velg tilfeldig 0 og 10||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(0, 10)
})
```

## Steg 5
Men et terningkast er kan ikke være et tall mellom 0 og 10.

Bytt ut ``0`` og ``10`` med ``1`` og ``6``.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
})
```

## Steg 6
Du skal nå inn på ``||loops:Løkker||`` og velge ``||loops:gjenta 4 ganger||``. Sett den inn under variabelen.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
    for (let index = 0; index < 4; index++) {}
})
```

## Steg 7
Endre ``4``-tallet til ``5`` i ``||loops:gjenta||``-blokken.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
    for (let index = 0; index < 5; index++) {}
})
```

## Info @showdialog
"Gjenta" betyr at det skjer om igjen.

## Steg 8
Inni ``||loops:gjenta||``-blokken skal du sette inn ``||basic:tøm skjerm||``, sette inn ``||basic:pause (ms) 100||`` og endre ``100``-tallet til ``200``.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
    for (let index = 0; index < 5; index++) {
        basic.clearScreen()
        basic.pause(200)
    }
})
```

## Steg 9a
Nå skal vi vise nummeret som er trekt. Begynn med å sette inn ``||basic:vis tall 0||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
    for (let index = 0; index < 5; index++) {
        basic.clearScreen()
        basic.pause(200)
        basic.showNumber(0)
    }
})
```

### Steg 9b
Gå til ``||variables:Variabler||``, trykk på ``Tilfeldig`` og dra den til ``0``-tallet, og bytt ut ``0`` med ``Tilfeldig``.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
    for (let index = 0; index < 5; index++) {
        basic.clearScreen()
        basic.pause(200)
        basic.showNumber(Tilfeldig)
    }
})
```

## Steg 10
På slutten setter du inn en ny pause på ``200`` millisekunder.

``` blocks
input.onButtonPressed(Button.A, function(){
    Tilfeldig = randint(1, 6)
    for (let index = 0; index < 5; index++) {
        basic.clearScreen()
        basic.pause(200)
        basic.showNumber(Tilfeldig)
        basic.pause(200)
    }
})
```

## Steg 11a
Når vi trykker på ``||input:knapp A+B||`` skal vi vise terning uten øyne på nytt.

Begynn med å sette inn ``||input:når knapp A+B trykkes||``.

``` blocks
input.onButtonPressed(Button.AB, function(){

})
```

### Steg 11b
Sett inn ``||basic:vis skjerm||`` og tegn på nytt en terning uten øyne.

``` blocks
input.onButtonPressed(Button.AB, function(){
    basic.showLeds(`
        # # # # #
        # . . . #
        # . . . #
        # . . . #
        # # # # #
        `)
})
```
