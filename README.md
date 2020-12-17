This data is used to configure building my 6001 Spanish Vocab anki deck.

### Interesting files:

# Building the deck

## Checkout tools and data
```bash
git clone https://github.com/doozan/spanish_tools
git clone https://github.com/doozan/spanish_data
git clone https://github.com/doozan/6001_Spanish spanish_custom
````
### Build the deck
```bash
    python3 -m spanish_tools.build_deck \
      --low-mem \
      --allforms spanish_data/es_allforms.csv \
      --dictionary spanish_data/es-en.data \
      --dictionary-custom spanish_custom/es-en.custom \
      --data-dir spanish_data \
      --custom-dir spanish_custom \
      --media ../cached.media \
      --short-defs spanish_custom/shortdefs.csv \
      --deckinfo spanish_custom/deck.json \
      --limit 6001 \
      -w spanish_data/frequency.csv \
      -w spanish_custom/extras.csv \
      -w spanish_custom/excludes.csv \
      --dump-sentence-ids spanish_custom/sentences.preferred \
      --dump-notes spanish_custom/notes.csv \
      --dump-credits spanish_custom/CREDITS \
      --dump-removed removed.txt \
      --anki "User 1" \
      jeffs_deck || return 1
# note: this is the exact command used by the build script, you probably don't want to use --low-mem, --dump-removed or --anki parameters
```
