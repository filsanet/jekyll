

## Problem Native Extensions

Removed these gems because the native dependencies cause them to fail under JRuby.

* fast-stemmer <- classifier
* posix-spawn <- pygments.rb
* redcarpet <- jekyll (for xhtml output)
* rdiscount

## Lost functionality and mitigation options

* pygments.rb -- syntax highlighting
    - Option 1: call native Python via JRuby's `backtick`
    - Option 2: call Jython/Pygments
    - Option 3: try a java-based alternative
        * https://code.google.com/p/jgments
        * https://code.google.com/p/jygments
* classifier - no "related posts" functionality
    - relies on native fast-stemmer
    - Option: rework classifier to use - https://github.com/caius/jruby-stemmer
* redcarpet, rdiscount are not a big problem -- kramdown provides equivalent functionality.

