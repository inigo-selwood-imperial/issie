# Inidivual Coding Report

#### Inigo Selwood `is1119` `01718768`

A report on the individual coding portion of my HLP coursework

## Summary

I've been working on [_BusWire.fs_](src/Renderer/DrawBlock/BusWire.fs), documenting and refactoring 32 functions covering 850+ lines of code. Those functions cover:

- Segment-related helpers
- Collision detection
- Autorouting
- Manual routing, both dragging and reduction/simplification

In every function I've tried to do the following:

- Produce consistent well-written XML docstrings and documentation
- Enforce 80-column line widths
- Give consistent type-hints for all functions
- Untangle dense blocks and match cases
- Where possible, replace conditional logic with pipelining

## Highlights

Listed here below are some of my favourite functions, those which I think I've done the best job of refactoring.

- `moveSegment`
- `getSafeDistanceForMove`
- `segmentIntersectsBoundingBoxCoordinates`

## To improve

While I've changed variable names for readability, I haven't touched function names for compliance with my teammates' work.

If it were my code base, I'd spread `BusWire.fs` out over two or three module files. It's a neater way of showing intent, and can shorten expressions. Having this many functions in a single file is difficult to navigate.

There's a few magic numbers littered about, mostly to do with checking for equality between floating point numbers. I didn't replace them with `System.Double.Epsilon` for fear that the resolution here matters, but it's something to think about.

Wires are hard-coded to have a maximum of 7 (6?) segments in them, which I think should be replaced with an arbitrary-length list.
