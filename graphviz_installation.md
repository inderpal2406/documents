## Graphviz is used to view terraform graph images of resources.

## Installation on Ubuntu 18.04 LTS x86_64 machine

`sudo apt install graphiz`

## Converting dot file to svg image file

`dot base.dot -Tsvg -o base.svg`

Here, `base.dot` file is the dot file generated from `terraform graph > base.dot` command and `base.svg` is the image file name after converting dot file to image file.
