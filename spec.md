# litelisp: a small, efficient, productive, and powerful lisp

first, read the [bnf](lisp.bnf)

## builtins

`(check-feature fstring)`: if it is possible to load the feature `fstring`, return `1`, else return `0`

`(feature fstring)`: tries to load the feature `fstring`, if it cannot load the feature, exits the app

`(cons a b)`: makes a `cons` cell of `a` and `b`

`(car cell)`: given a `cons` cell `cell`, returns the value of `a`

`(cdr cell)`: given a `cons` cell `cell`, returns the value of `b`

`(+ x y)`: adds `x` and `y`

`(- x y)`: subtracts `x` from `y`

`(* x y)`: multiplys `x` and `y`

`(/ x y)`: divides `x` by `y`

`(< x y)`: if `x` is less than `y`, then returns `1`, else returns `0`

`(= x y)`: if `x` equals `y`, then returns `1`, else returns `0`

`(> x y)`: if `x` is greater than `y`, then returns `1`, else returns `0`

`(function arglist codelist)`: returns a function, for example:
```
(log-info ((function (x) (x)) 1))
(ignore "logs 1")
```

`(log-info info)`: self-documenting

`(log-error error)`: also self-documenting

`(set varname_str value)`: sets the variable `varname_str` to the value `value`, to reference it, use the atom of the value of `varname_str`, and unscopes when the it leaves the current scope, for example:
```
(set "axe" "axer")
(log-info axe)
(ignore "logs axer")
```