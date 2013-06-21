# lunr Index Builder

A simple command line tool for building lunr indexes.

## Installation

    npm install lunr-index-build

## Usage

    Generates a lunr.js index.

      lunr-index-build -r id -f title:10 -f body < data.json > index.json

    Options:
      -f, --field  Specify a field to index                               [required]
      -r, --ref    Specify the field that will be the document reference

`lunr-index-builder` reads your data from stdin and outputs a built index on stdout. You need to specify some fields to index from your input data and, optionally the ref for the documents. These options map directly to those of [lunr.js](http://lunrjs.com) itself so see that documentation for more details.

The input is expected to be valid JSON, with an array of document objects, e.g

    [{
        "id": 1,
        "title": "Foo"
    },{
        "id": 2,
        "title": "Bar"
    }]

### Example

    $ lunr-index-builder --field title:10 --field tags:100 --field body --ref id < data.json > index.json



