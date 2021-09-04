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
      --model spanish_custom/card_model.json \
      --deck-guid 1091781313372 \
      --deck-name "Jeff's Spanish::6001" \
      --deck-desc "The 6001 most frequently used Spanish words - with audio, comprehensive definitions, and usage sentences. Compiled by Jeff Doozan" \
      -w spanish_data/frequency.csv \
      -w spanish_custom/replacements.csv \
      -w spanish_custom/extras.csv \
      -w spanish_custom/exclude_common.csv \
      -w spanish_custom/excludes.csv \
      --limit 6001 \
      --allow-flag LITERAL \
      --dump-sentence-ids spanish_custom/sentences.preferred \
      --dump-notes spanish_custom/notes.csv \
      --dump-credits spanish_custom/CREDITS \
      jeffs_deck || return 1
# note: this is the exact command used by the build script, you probably don't want to use --low-mem
```
