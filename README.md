# lhs-rhs [TODO]

A small, bare-bones implementation similar to if-diff, that can "morph" into if-diff when if-diff is ready, thus reducing time to interactive.

Best if used in combination with server-rendered content.

```html
<lhs-rhs -if -lhs -eq -rhs set-attr=data-is-monday set-class=monday--blues -while-matches -until-matches -m></lhs-rhs>
```

When "if" is true, and "lhs"=="rhs", the next sibling(s)'s "data-is-monday" attribute is set.  If it is false, attribute is removed.  Likewise with set-class.

Optionally, can proceed down the sibling list as long as "while-matches" css selector is satisfied, or "until-matches" css selector is found (not inclusive?).  If both while-matches and until-matches are specified, both must be satisfied.  Also, m is a circuit breaker, providing upper bound to how many elements to affect.


Missing features from if-diff:

1.  No built-in mutation observer (remove from if-diff as well).  But like on-to-me, can re-evaluate if "nudged" by a mutation observer.
2.  No fancy object comparison.
3.  if, lhs, rhs, m are properties, not attributes (as they are not restricted to strings).
4.  Others are attributes, not properties

