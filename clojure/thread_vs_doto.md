# Thread `->` vs. `doto`

I ran into an issue when trying to thread (`->`) an atom.

```plaintext
user=> (def foo (atom 2))
#'user/foo
user=> (-> foo
           (swap! inc)
           (swap! square))
ClassCastException java.lang.Long cannot be cast to clojure.lang.Atom
```

Taken from the documentation of `swap!`

> Returns the value that was swapped in.

```plaintext
user=> (class foo)
clojure.lang.Atom
user=> (class (swap! foo inc))
java.lang.Long
```

:confused: You cannot simply thread an atom through functions which perform on atoms.

You can however, use `doto`.

```plaintext
user=> (doto foo
             (swap! inc)
             (swap! square))
#<Atom@3cdb26ad: 9>
```

:bulb: In summary, use `doto` for side effects and mutable objects.

:tada: Happy coding!
