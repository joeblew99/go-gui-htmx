
# https://github.com/ajstarks/decksh/tree/master/cmd/decksh
SRC_DECK_SH=github.com/ajstarks/decksh.git//cmd/decksh/

# https://github.com/ajstarks/deck/tree/master/cmd/pdfdeck
SRC_DECK_PDF=github.com/ajstarks/deck.git//cmd/pdfdeck

# https://github.com/ajstarks/deck/tree/master/cmd/svgdeck
SRC_DECK_SVG=github.com/ajstarks/deck.git//cmd/svgdeck

# https://github.com/ajstarks/giocanvas/tree/master/gcdeck
SRC_DECK_GIO=github.com/ajstarks/giocanvas.git//gcdeck/

OUT_DECK_SH=$(PWD)/deck-sh
OUT_DECK_PDF=$(PWD)/deck-pdf
OUT_DECK_SVG=$(PWD)/deck-svg
OUT_DECK_GIO=$(PWD)/deck-gio

BIN_ROOT=$(PWD)/.bin
export PATH:=$(PATH):$(BIN_ROOT)

BIN_DECK_SH_NAME=deck-sh
BIN_DECK_SH=$(BIN_ROOT)/$(BIN_DECK_SH_NAME)

BIN_DECK_PDF_NAME=deck-pdf
BIN_DECK_PDF=$(BIN_ROOT)/$(BIN_DECK_PDF_NAME)

BIN_DECK_SVG_NAME=deck-svg
BIN_DECK_SVG=$(BIN_ROOT)/$(BIN_DECK_SVG_NAME)

BIN_DECK_GIO_NAME=deck-gio
BIN_DECK_GIO=$(BIN_ROOT)/$(BIN_DECK_GIO_NAME)

print:
	ls -al $(OUT_DECK_SH)

all: dep 
dep:
	# https://github.com/hashicorp/go-getter
	# latest is kinf of broken...
	#go install github.com/hashicorp/go-getter/cmd/go-getter@latest
	go install github.com/hashicorp/go-getter/cmd/go-getter@v1.7.1

	go install github.com/oligot/go-mod-upgrade@latest

### EXTRACT
	
extract-all-del:
	rm -rf $(OUT_DECK_SH)
	rm -rf $(OUT_DECK_PDF)
	rm -rf $(OUT_DECK_SVG)
	rm -rf $(OUT_DECK_GIO)

extract-all: extract-all-del extract-deck-sh extract-deck-pdf extract-deck-svg extract-deck-gio

extract-deck-sh: 
	# https://github.com/hashicorp/go-getter/blob/main/README.md#subdirectories
	mkdir -p $(OUT_DECK_SH)
	go-getter $(SRC_DECK_SH) $(OUT_DECK_SH)
	rm -rf $(OUT_DECK_SH)/binaries
	cd $(OUT_DECK_SH) && go mod init main

extract-deck-pdf:
	mkdir -p $(OUT_DECK_PDF)
	go-getter $(SRC_DECK_PDF) $(OUT_DECK_PDF)
	rm -rf $(OUT_DECK_PDF)/binaries
	cd $(OUT_DECK_PDF) && go mod init main

extract-deck-svg:
	mkdir -p $(OUT_DECK_SVG)
	go-getter $(SRC_DECK_SVG) $(OUT_DECK_SVG)
	rm -rf $(OUT_DECK_SVG)/binaries
	cd $(OUT_DECK_SVG) && go mod init main

extract-deck-gio:
	mkdir -p $(OUT_DECK_GIO)
	go-getter $(SRC_DECK_GIO) $(OUT_DECK_GIO)
	rm -rf $(OUT_DECK_GIO)/binaries
	cd $(OUT_DECK_GIO) && go mod init main
	
### BUILD

build-all-del:
	rm -rf $(BIN_ROOT)
build-all: build-all-del build-deck-sh build-deck-pdf build-deck-svg build-deck-gio

build-deck-sh:
	cd $(OUT_DECK_SH) && go mod tidy
	cd $(OUT_DECK_SH) && go build -o $(BIN_DECK_SH) .
build-deck-pdf:
	cd $(OUT_DECK_PDF) && go mod tidy
	cd $(OUT_DECK_PDF) && go build -o $(BIN_DECK_PDF) .
build-deck-svg:
	cd $(OUT_DECK_SVG) && go mod tidy
	cd $(OUT_DECK_SVG) && go build -o $(BIN_DECK_SVG) .
build-deck-gio:
	cd $(OUT_DECK_GIO) && go mod tidy
	cd $(OUT_DECK_GIO) && go build -o $(BIN_DECK_GIO) .

## RUN

run-deck-sh:
	$(BIN_DECK_SH_NAME) -h
run-deck-pdf:
	$(BIN_DECK_PDF_NAME) -h
run-deck-svg:
	$(BIN_DECK_SVG_NAME) -h
run-deck-gio:
	$(BIN_DECK_GIO_NAME) -h

### TEST

# todo. just exercise them usng pipes.


