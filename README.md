
# halzu

A LaTeX package for typesetting "split annotation" (Halzu, 할주, 割註, Warichu),
a traditional CJK typographic convention of typesetting various notes in small
double lines. It is (or was) frequently used, among others, in law books.

The package requires:

- pdfTeX, XeTeX, or LuaTeX engine
- LaTeX format
- `zref-savepos` package

## Usage

In preamble:
```
\usepackage{halzu}
```
and in the body of document:
```
\halzulower{0pt}% optional
\halzusize{0.7}% optional
\halzu{...}
```

```
\def\halzulower{0pt}
```
makes all Halzu boxes move downwards by the amount specified.
`0pt` is the default. Negative value is also acceptable.

```
\def\halzusize{0.7}
```
denotes the factor between the current document font size and the Halzu font.
The default value is `0.7`, the same as `scriptsize`.

## License

Public Domain.
