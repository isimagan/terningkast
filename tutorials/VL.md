# Terningkast - Veldig lett

## Steg 1
Vi begynner med å tegne en terning uten øyne som skal vises ``||basic:ved start||``.

``` blocks
basic.showLeds(`
    # # # # #
    # . . . #
    # . . . #
    # . . . #
    # # # # #
    `)
```

## Steg 2
Når vi trykker på ``||input:knapp A||`` skal vi vise hva vi kastet. Kastet er et tilfeldig tall mellom 1 og 6.

Begynn med å sette inn ``||input:når knapp A trykkes||``.

``` blocks
input.onButtonPressed(Button.A, function () { })
```

## Steg 3
Sett inn ``||basic:vis tall||``.

``` blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(0)
})
```

## Steg 4
I stedet for ``0``
skal vi ha et tilfeldig tall. Du finner ``||math:tilfeldig tall||``
under ``Matematikk``.

``` blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(randint(0, 10))
})
```

## Steg 5
Nå vil den velge et tilfeldig tall mellom 0 og 10. Det er ikke det vi ønsker, for en terning går fra 1 til 6.

Bytt ut ``0``
og ``10``
med ``1``
og ``6``.

``` blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(randint(1, 6))
})
```

## Steg 6
Vi vil at når vi trykker på ``||input:knapp A og B||`` skal micro:biten resettes.

Sett inn ``||input:når knapp A+B trykkes||``.

``` blocks
input.onButtonPressed(Button.AB, function () { })
```

### Hvordan gjøre det - Steg 1
Sett inn ``||input:når knapp A trykkes||``.

``` blocks
input.onButtonPressed(Button.A, function(){})
```

### Steg 2
Ved siden av ``||input:A||`` er det en liten, hvit pil. Trykk på den og velg ``||input:A+B||``.

![Knappeliste](https://isimagan.github.io/terningkast/AfL/KnappAB.png)

## Steg 7
Inni her setter vi inn på nytt en terning uten øyne.

``` blocks
input.onButtonPressed(Button.AB, function () {
    basic.showLeds(`
        # # # # #
        # . . . #
        # . . . #
        # . . . #
        # # # # #
        `)
})
```
