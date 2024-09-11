# Thumbhash Test Data

This directory holds the https://evanw.github.io/thumbhash/ examples as
individual files.

The `*.th` files hold thumbhash-encoded data, prepended with a 3-byte magic
string so that `/usr/bin/file` (if its Magdir database was updated) or similar
programs can identify the data as thumbhash-formatted data.

That 3-byte magic string is "\xC3\xBE\xFE", which is arbitrary and not part of
the original thumbhash description or implementation. But "\xC3\xBE" is the
UTF-8 encoding of 'þ' (U+00FE LATIN SMALL LETTER THORN) and "\xFE" is invalid
UTF-8 but is the ISO-8859-1 encoding of 'þ'. The Old English letter 'þ' is
pronounced like the "th" that starts "thumbhash".

The `*.png` files hold the decodings of the `*.th` files, as produced by that
web page. Its JavaScript PNG encoder favors implementation simplicity over
maximizing compression ratio.

The filenames' base names are the base64url encoding (similar to but slightly
different from the base64std encoding used on that web page) of the thumbhash
data (without the magic string).
