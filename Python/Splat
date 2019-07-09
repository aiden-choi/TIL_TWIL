From https://stackoverflow.com/questions/5239856/asterisk-in-function-call

* is the "splat" operator: It takes a list as input, and expands it into actual positional arguments in the function call.

So if uniqueCrossTabs was [ [ 1, 2 ], [ 3, 4 ] ], then itertools.chain(*uniqueCrossTabs) is the same as saying itertools.chain([ 1, 2 ], [ 3, 4 ])

This is obviously different from passing in just uniqueCrossTabs. In your case, you have a list of lists that you wish to flatten; what itertools.chain() does is return an iterator over the concatenation of all the positional arguments you pass to it, where each positional argument is iterable in its own right.

In other words, you want to pass each list in uniqueCrossTabs as an argument to chain(), which will chain them together, but you don't have the lists in separate variables, so you use the * operator to expand the list of lists into several list arguments.

As Jochen Ritzel has pointed out in the comments, chain.from_iterable() is better-suited for this operation, as it assumes a single iterable of iterables to begin with. Your code then becomes simply:

uniqueCrossTabs = list(itertools.chain.from_iterable(uniqueCrossTabs))

----------------
Thus using * and without using * makes different output (and input) for function call.
