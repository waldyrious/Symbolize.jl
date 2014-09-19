# Symbolize

[![Build Status](https://travis-ci.org/waldyrious/Symbolize.jl.svg?branch=master)](https://travis-ci.org/waldyrious/Symbolize.jl)

Symbolize is a [Julia](http://julialang.org) package to perform numeric-to-symbolic inference
(aka "reverse calculation"), i.e., [convert a number to a closed-form representation]
(https://en.wikipedia.org/wiki/Closed-form_expression#Conversion_from_numerical_forms).


The goal is to emulate tools like `identify` from
[Maple](http://www.maplesoft.com/support/help/Maple/view.aspx?path=identify) and
[SymPy](http://docs.sympy.org/latest/modules/mpmath/identification.html#mpmath.identify);
ISC [v1](http://oldweb.cecm.sfu.ca/projects/ISC/ISCmain.html) and [v2](http://isc.carma.newcastle.edu.au/);
and [RIES](http://mrob.com/pub/ries/index.html) (the one used in the making of [this xkcd comic](http://xkcd.com/1047/)), to get a [closed-form](https://en.wikipedia.org/wiki/Closed-form_expression) representation of a number, if possible.

The plan is to start small, first by
[identifying multiples of known constants](https://github.com/sunetos/TextPlots.jl/blob/0e8be9d/src/plot.jl#L14)
and [simple fractions](http://docs.julialang.org/en/latest/stdlib/base/#Base.rationalize),
and then gradually go up the [hierarchy of mathematical expressions](https://en.wikipedia.org/wiki/Template:Mathematical_expressions)
as well as adopting whatever other strategies or heuristics from the tools listed above.
I'm not yet sure how far along it will be feasible to go,
but it seemed like a fun idea to try.

Eventually, it could even move beyond single numbers, and deal with vectors,
in essence attempting to figure out the mathematical model most likely behind a stream of data,
such as finding the equations governing an oscillating signal based on a bunch of measured samples
(this kind of application is called [Symbolic regression](https://en.wikipedia.org/wiki/Symbolic_regression)).
