# spec

gio and bubble tea ( low priority ) as it does not have a markup description.

## Deck 

Its very very simple in a good way and provides a markup language for golang gio apps

gio: https://github.com/ajstarks/decksh/blob/master/cmd/decksh/decksh.go outpts the xml

Renderers consume the xml:

- app renderer: https://github.com/ajstarks/giocanvas/blob/master/gcdeck/main.go 

- pdf renderer:  https://github.com/ajstarks/deck/blob/master/cmd/pdfdeck/pdfdeck.go

- png renderer: https://github.com/ajstarks/deck/blob/master/cmd/pngdeck/pngdeck.go

Deck renders the basics, and we woudl add thinks like Flex layout etc, which gio has.

We woudl then add the actions required to allow making any element reactive.

## HTMX 

https://github.com/kyoto-framework/kyoto 

client code is simple: https://github.com/kyoto-framework/kyoto/blob/master/client/src/client.ts

Actions is the important part: https://kyoto.codes/kyoto/actions.html
