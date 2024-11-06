# Returned from `swap!`

From the documentation of `swap!`.

> Returns the value that was swapped in.

```plaintext
user=> (def foo (atom 0))
#'user/foo
user=> (swap! foo inc)
1
```

OK, that seems right.

How about this?

```plaintext
user=> (def bar (atom {}))
#'user/bar
user=> (swap! bar assoc :a 0)
{:a 0}
user=> (swap! bar assoc :b 1)
{:b 1, :a 0}
```

:confused: That seems a bit odd. I thought I had _swapped in_ `{:b 1}` but the entire Map was returned.

:bulb: This is because `assoc` _swaps in_ an entirely new Map.

:tada: Happy coding!
