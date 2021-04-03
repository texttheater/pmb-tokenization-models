pmb-tokenization-models
=======================

Scripts to create tokenization (and sentence segmentation) models for the
[Parallel Meaning Bank](https://pmb.let.rug.nl/) (PMB). Uses the
[Elephant](https://gmb.let.rug.nl/elephant/) tokenizer.

Currently creates a model trained on the English gold data.

Coming soon: other languages, training on silver data.

Usage
-----

Make sure submodules are present:

	git submodule update --init --recursive

Compile Elephant and its dependencies:

	cd elephant
	make
	cd ..

[https://pmb.let.rug.nl/data.php](Download) the PMB 3.0.0 and unzip (or
symlink) the `pmb-3.0.0` directory into this repository root.

Optionally (but strongly recommended), switch to a dedicated Python 3 virtual
environment. Then install the dependencies:

	pip3 install -r requirements.txt

Run the training code:

	produce

This will create the directory `out/en.train.gold.model`, containing a model
for Elephant trained on the English gold data.
