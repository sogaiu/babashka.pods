# babashka.pods

A library to load babashka pods. Used by babashka but also usable from the JVM
or other [sci](https://github.com/borkdude/sci)-based projects.

## Usage

On the JVM:

``` clojure
(require '[babashka.pods.jvm :as pods])
(pods/load-pod "pod-babashka-hsqldb")
(require '[pod.babashka.hsqldb :as sql])

(def db "jdbc:hsqldb:mem:testdb;sql.syntax_mys=true")
(sql/execute! db ["create table foo ( foo int );"])
;;=> [#:next.jdbc{:update-count 0}]
```

From the [Small Clojure Interpreter](https://github.com/borkdude/sci):

See [test/babashka/pods/sci_test.clj](test/babashka/pods/sci_test.clj).

## License

Copyright © 2020 Michiel Borkent

Distributed under the EPL License. See LICENSE.
