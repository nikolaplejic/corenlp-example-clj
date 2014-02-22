# corenlp-example-clj

...in which I play around with Stanford CoreNLP and try to get it up & running in Clojure.

From the [Stanford CoreNLP website](nlp.stanford.edu/software/corenlp.shtml):

> Stanford CoreNLP provides a set of natural language analysis tools which can take raw English language text input and give the base forms of words, their parts of speech, whether they are names of companies, people, etc., normalize dates, times, and numeric quantities, and mark up the structure of sentences in terms of phrases and word dependencies, and indicate which noun phrases refer to the same entities.

**Note:** This will download both CoreNLP and the models it needs to do its magic, which is approx. 200 MB of data.

## Usage

To run the example with the default text, which is

> Look at this beautiful sentence we're about to parse! Isn't Stanford's CoreNLP great?

    $ lein run

See the project.clj file for details on how to add CoreNLP as a dependency to your Clojure project.

See the core.clj file for the API Example from [Stanford's CoreNLP homepage](http://nlp.stanford.edu/software/corenlp.shtml) translated into something resembling Clojure.

The example itself is a function, `run-example`, so you can play around with it in the REPL:

    $ lein repl
    corenlp-example-clj.core=> (run-example "I will not buy this record, it is scratched. My hovercraft is full of eels.")

The output of the function is a pretty-printed:

  1. coreference link graph of the entire text
  2. for each sentence:
    1. the parse tree of the sentence
    2. the Stanford dependency graph of the sentence
    3. for each token in the sentence:
      1. the text of the token
      2. the POS tag of the token
      3. the NER label of the token

## License

CoreNLP is distributed under GPL v2+.  This example follows its licensing and is:

Distributed under the [GNU General Public License](http://www.gnu.org/licenses/gpl-2.0.html) (v2 or later).
