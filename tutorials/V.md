# Terningkast - Vanskelig

## Hva skal skje? @showdialog
Vi skal
- Vise tallene 1-6
- Vise en terning uten øyne
- Når knapp A trykkes
    - se om du allerede har kastet
    - vise et tilfeldig tall mellom 1 og 6 ti ganger
    - vise det siste tilfeldige tallet og få det til å blinke fem ganger
- Når knapp A+B trykkes
    - Sørge for at vi kan kaste på nytt

## Forberedelser
- Slett ``||basic:gjenta for alltid||``
- Trykk på ``||variables:Variabler||`` og lag disse variablene:
    - ``Kast``
    - ``Tilfeldig``

I ``||basic:ved start||`` setter du inn at ``||variables:Kast||`` skal være ``0``.

``` blocks
Kast = 0
```

## Vise tallene 1 til 6 - Steg 1a
Gå inn på ``||loops:Løkker||`` og sett inn ``||loops:gjenta for indeks 0 til 4||``.

Denne blokker teller tallene fra 0 til 4, altså 0, 1, 2, 3 og 4. Dette er fem sifre. Men vi skal telle til seks, så for å få seks sifre må du endre ``4`` til ``5``, slik at den teller 0, 1, 2, 3, 4 og 5.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 4; indeks++) {

}
```

### Steg 1b
Bytt ut ``4`` med ``5``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {

}
```

## Steg 2a
Det tallet vi teller er ``||variables:indeks||``. Ser du den i ``||loops:gjenta||``-blokken?

Vi skal vise dette tallet. Men vi vil ikke telle fra 0 til 5, men fra 1 til 6. Derfor skal vi sette inn ``||basic:vis tall||`` ``||variables:indeks||`` ``+ 1``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(0)
}
```

### Steg 2b
Gå inn på ``||math:Matematikk||``, finn ``||math:0 + 0||`` og sett inn denne i stedet for ``0``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(0 + 0)
}
```

### Steg 2c
Bytt ut første ``0`` med ``||variables:indeks||``. Dette gjør du med å dra ``||variables:indeks||`` ned til ``0``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 0)
}
```

### Sted 2d
Bytt ut den bakerste ``0`` med ``1``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
}
```

## Steg 3a
Vi vil ikke at tallet skal endre seg med en gang, så sett inn en ``||basic:pause (ms)||`` på 500 ms.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
    basic.pause(100)
}
```

### Steg 3b
Bytt ut ``100`` med ``500``.

``` blocks
Kast = 0
for (let indeks = 0; indeks <= 5; indeks++) {
    basic.showNumber(indeks + 1)
    basic.pause(500)
}
```

## Vise en terning uten øyne
Under ``||loops:gjenta||``-blokken setter du inn ``||basic:vis skjerm||`` og tegner en terning uten øyne.

``` blocks
Kast = 0
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

## Se om du allerede har kastet @showdialog
``||variables:Kast||`` sier om du har kastet eller ikke. Vis den er
- ``0`` har du ikke kastet
- ``1`` har du kastet

## Steg 1
Dette skal vi sjekke først når vi har trykket på ``||input:knapp A||``. Så sett inn blokken ``||input:når knapp A trykkes||``

``` blocks
input.onButtonPressed(Button.A, function(){

})
```

## Steg 2a
Sjekk om du har kastet. Vi går til ``||logic:Logikk||`` og setter inn en ``||logic:hvis sann så||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (true) {

    }
})
```

### Steg 2b
Gå tilbake til ``||logic:Løkker||``, finn ``||logic:0 = 0||`` og sett den inn i stedet for ``sann``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (0 == 0) {
        
    }
})
```

### Steg 2c
Bytt ut første ``0`` med ``||variables:Kast||``

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        
    }
})
```

## Vise et tilfeldig tall mellom 1 og 6 ti ganger - Steg 1a
Gå til ``||loops:Løkker||``, finn ``||loops:gjenta 4 ganger||`` og sett den inn i ``||logic:hvis||``-blokken. Endre ``4`` til ``10``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 4; index++) {}
    }
})
```

### Steg 1b
Bytt ut ``4`` med ``10``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {

        }
    }
})
```

## Steg 2a
Sett inn ``||basic:vis tall||``, og tallet du skal vise er et tilfeldig tall mellom 1 og 6.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(0)
        }
    }
})
```

### Steg 2b
Gå til ``||math:Matematikk||``, finn ``||math:velg tilfeldig 0 til 10||`` og sett den inn i stedet for ``0``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(randint(0, 10))
        }
    }
})
```

### Steg 2c
Bytt ut ``0 og 10`` med ``1 og 6``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(randint(1, 6))
        }
    }
})
```

## Steg 3
Vi vil at tallet skal endres raskt, så under setter du inn en pause på 100 ms.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(randint(1, 6))
            basic.pause(100)
        }
    }
})
```

## Få siste tall til å blinke fem ganger - Steg 1
Det siste tallet vil vi at skal blinke. Først setter vi ``||variables:Tilfeldig||`` til et tilfeldig tall mellom 1 og 6, slik vi nettopp gjorde med ``||basic:vis tall||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(randint(1, 6))
            basic.pause(100)
        }
        Tilfeldig = randint(1, 6)
    }
})
```

## Steg 2
Tallet skal blinke fem ganger. Sett inn en ny ``||loops:gjenta||``-blokk, og endre tallet til ``5``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(randint(1, 6))
            basic.pause(100)
        }
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
        
        }
    }
})
```

## Informasjon @showdialog
Nå kommer jeg ikke til å vise ``||loops:gjenta 10 ganger||``, men den skal ikke fjernes.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
        
        }
    }
})
```

## Steg 3
Begynn med å ``||basic:tømme skjermen||``, og sett inn en ``||basic:pause (ms)||`` på 500 ms.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(500)
        }
    }
})
```

## Steg 4
Nå skal vi vise tallet ``||variables:Tilfeldig||``. Sett inn ``||basic:vis tall||`` og bytt ut ``0`` med ``||variables:Tilfeldig||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(500)
            basic.showNumber(Tilfeldig)
        }
    }
})
```

## Steg 5
Sett inn en ny pause på 500 ms.

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(500)
            basic.showNumber(Tilfeldig)
            basic.pause(500)
        }
    }
})
```

## Resultat @showdialog
Det skal nå se slik ut:

``` blocks
input.onButtonPressed(Button.A, function(){
    if (Kast == 0) {
        for (let index = 0; index < 10; index++) {
            basic.showNumber(randint(1, 6))
            basic.pause(100)
        }
        Tilfeldig = randint(1, 6)
        for (let index = 0; index < 5; index++) {
            basic.clearScreen()
            basic.pause(500)
            basic.showNumber(Tilfeldig)
            basic.pause(500)
        }
    }
})
```

## Nytt kast - Steg 1
For å kaste et nytt kast må vi trykke på ``||input:knapp A+B||``. Sett inn riktig blokk.

``` blocks
input.onButtonPressed(Button.AB, function(){

})
```

## Steg 2
``||variables:Kast||`` er ``1`` siden vi har kastet. Endre denne tilbake til ``0``.

``` blocks
input.onButtonPressed(Button.AB, function(){
    Kast = 0
})
```

## Steg 3
Vis på nytt en terning uten øyne.

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
