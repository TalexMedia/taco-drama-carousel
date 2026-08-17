# Taco Drama — LinkedIn carousel

Talex Media. Eight slides, 1080x1350 (4:5 portrait), built in the Claude Design
deck system and flattened to standalone HTML.

| File | What it is |
|---|---|
| `index.html` | The locked deck. No editing layer. |
| `edit.html` | Tom's review copy. Click any text to edit; saves automatically. |
| `taco-drama-carousel.pdf` | The export, ready to upload as a LinkedIn document post. |

## Reviewing

<https://talexmedia.github.io/taco-drama-carousel/edit.html>

Edits save to the cloud as you type, so there is nothing to send back. The
"Export Final Version" button downloads a locked copy if you want one.

Anyone with that link can edit the deck, so keep it to the review group.

## Rebuilding

From `ProspectAudit/` in the Talex workspace:

```
node tools/deck-unbundle.mjs --input <saved-artifact>.html --out decks/taco-drama/index.html
python tools/editable-mode.py --input decks/taco-drama/index.html --slug taco-drama \
    --storage firebase --firebase-config firebase.json --output decks/taco-drama/edit.html
node tools/carousel-pdf.mjs --input decks/taco-drama/index.html
```

Draft key: `taco-drama-975a7462`. Pull Tom's edits back with `tools/publish-final.py`.

Every page of a LinkedIn document must share one page size, so never mix slide
ratios inside a deck.
