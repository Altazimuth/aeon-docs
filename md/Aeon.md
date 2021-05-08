# AngelScript Language

Aeon uses the [AngelScript](http://www.angelcode.com/angelscript/) scripting
language, which first appeared in 2003 and has found use in many games, being
the scripting language of choice for Nightdive Studio's
[Kex Engine](https://www.nightdivestudios.com/kex/). It most closely resembles
C++, but with some features omitted and extensions added.

This documentation serves as an introduction to and informal specification of
the AngelScript language from a programmer's viewpoint. It should also be useful
for non-programmers looking for specifics on the inner workings of the language
and more information on the functions and properties provided to it.

AngelScript runs in a virtual machine much like ACS, but unlike ACS is compiled
from source and compiled into bytecode when Eternity starts up. Whilst it is
possible to pre-compile AngelScript to bytecode Eternity does not support this,
and so Aeon can only be read from source files by the engine.

## Reading This Document

This document's syntax definitions are written to be easy to read but
still close enough to a formal syntax that, for instance, someone
writing a parser could do so off of this document. Here is a legend
describing all syntax element spellings:

| Spelling | Meaning
| :------- | :------
| `Symbol` | Any symbol in `monospace` is spelled as-is.
| Syntax | Any syntax definition defined by this document.
| * | A syntax element of which there may be any amount of.
| + | A syntax element of which there may be one or more of.
| ? | An optional element, which may be omitted.
| {N} | A syntax element of which there may be exactly N amount of.
| {N..M} | A syntax element of which there may be between N and M of, inclusive.
| (Element) | A sequence of elements that may have modifiers such as * or + applied to them.
| List items or "," | Alternatives available for this element.

Some example syntax definitions would be:

<dl class="syn"><dt>ExampleElement</dt><dd>

`keyword` SomeKeyword (`,` SomeKeyword)? `;`

</dd><dt>SomeKeyword</dt><dd>

* `example`
* `example2`
* `example3`

</dd></dl>

Which would mean, in Aeon, you could write things like:

```aeon
keyword example;
keyword example2, example3;
```
