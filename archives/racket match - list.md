# Racket match -- (list lvp ...) pattern

## The (list lvp ...) pattern

Example, what's the result:

~~~scheme
(match '(1 2 3)
  [(list x ...) x])
~~~

Is it `1`?

No! The right answer is :

~~~
'(1 2 3)
~~~

Look at the reference:
> **(list lvp ...)** — matches a list of elements. In the case of (list pat ...), the pattern **_matches a list with as many element as pats_**, and each element must match the corresponding pat. In the more general case, each lvp corresponds to a “spliced” list of greedy matches.

~~~scheme
> (match '(1 2 3)
    [(list x y ...) y])
'(2 3)

> (match '(1 2 3)
    [(list x y _ ...) y])
2
~~~
