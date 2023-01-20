pmb-tokenization-models
=======================

Scripts to create tokenization (and sentence segmentation) models for the
[Parallel Meaning Bank](https://pmb.let.rug.nl/) (PMB). Uses the
[Elephant](https://gmb.let.rug.nl/elephant/) tokenizer.

Usage
-----

Make sure submodules are present:

    git submodule update --init --recursive

Compile Elephant and its dependencies:

    cd elephant
    make
    cd ..

Optionally (but strongly recommended), switch to a dedicated Python 3 virtual
environment. Then install the dependencies:

    pip3 install -r requirements.txt

Run the training code:

    produce

This will create models for English, German, Italian, and Dutch.

You can also create model outputs for the PMB development and test data in
`.tok.iob` and `.tok` format. For example, to get predictions for the German
development data in `.tok` format:

    produce out/pmb-3.0.0-de-gold-dev.tok

Limitations
-----------

* Currently only uses gold data for English and German, silver data for Italian
  and Dutch
* The character-level LLMs used are still the same ones used in the original
  Elephant release. In particular, there is no LLM for German, so we use the
  Dutch one instead.

Data
----

The data shipped in this repo have been extracted from the Parallel Meaning
Bank using [pmb2tsv](https://github.com/texttheater/pmb2tsv).
