python-bchlib [![Build Status](https://travis-ci.com/jkent/python-bchlib.svg?branch=master)](https://travis-ci.com/jkent/python-bchlib)
=============

This is a python module for encoding and correcting data using [BCH codes](https://en.wikipedia.org/wiki/BCH_code).  This is a fork of https://github.com/jkent/python-bchlib that extends support for Galois Field orders up to 31 (previous implementation supported up to 15).
And also update bch source code from kernel source tree.

## Requirements
  For Windows, python3.5 or greater required.<br>
  For Linux and MacOS, python2.7 or python3.4 or greater required.

## Installing the latest release:
    $ pip install bchlib

## Installing from source:
  Make sure you have python-dev setup.  For Windows, this means you need [Visual Studio 2015](https://stackoverflow.com/a/44290942/6844002).

    $ pip install .

## Module Documentation
bchlib.__BCH(__ polynomial, t[, reverse] __)__ → bch
> Constructor creates a BCH object with given `polynomial` and `t` bit strength, `reverse` is an optional boolean that flips the bit order of data. The Galois field order is automatically determined from the `polynomial`.

bch.__encode(__ data[, ecc] __)__ → ecc
> Encodes `data` with an optional starting `ecc` and returns an ecc.

bch.__decode(__ data, ecc __)__ → ( bitflips, data, ecc )
> Corrects `data` using `ecc` and returns a tuple.

bch.__decode_inplace(__ data, ecc __)__ → bitflips
> Corrects `data` using `ecc` in place, returning the number of bitflips.

bch.__decode_syndromes(__ data, syndromes __)__ → ( bitflips, data )
> Corrects `data` using a sequence of `syndromes`, of t*2 elements, returning a tuple.

bch.__compute_even_syndromes(__ syndromes __)__ → syndromes
> Computes even syndromes from odd ones. Takes and returns a sequence of t*2 elements.

bch.__ecc_bytes__
> A readonly field; the number of bytes an ecc takes up.

bch.__ecc_bits__
> A readonly field; the number of bits an ecc takes up.

bch.__m__
> A readonly field; the Galois field order.

bch.__n__
> A readonly field; the maximum codeword size in bits.

bch.__syndromes__
> A readonly field; a tuple of syndromes after performing a correct operation.

bch.__t__
> A readonly field; the number bit errors that can be corrected.

## Usage Example
  Look at test.py

