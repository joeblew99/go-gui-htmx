# todo

- do this all as a mono repo to make life easy.

- clean up deck
  - make a subfolder called decky.
  - write a script to extract only what we need out of the deck repos, because they are full of lots of exampples
  - write a make script to extract the examples to a different repo.
 
- make a basic gui in gio to run decksh examples easily.
  - this is a gio ui that can display a tree that represents the file system, so we can easily run deck gio canvas.
  - this will give us a basis to add reactivit later.
  - left pane: tree view of foolders
  - mid pane: deck gio canvas ( laetr we make this a webview ), so we can load different versions of deck so that schema evolution never becomes an issue.
  - right pane: tree view of properties of a deck file
  - tech:
    - https://github.com/ajstarks/deck/tree/master/cmd/deckd has the basic we need

- make the decksh changable
  - as you change properties, they are sent back to the decksh file and updated usng Unified diff ( git )
  - then the GUI updates the hwole page ( for now ), as we dont have the htmx aspects yet.
  - tech:
    - Unified diff
   
- htmx aspects
  - Concept: this is using the deck xml, not the decksh because the GUI is already designed in dekcsh, and now we jsut want to do htmx on top of it via deck xml
  - ...
