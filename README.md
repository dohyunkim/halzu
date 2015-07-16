
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
\halzu{...}
```

The only user command for configuration is `\halzulower{...}`, by which
all Halzu boxes will move downwards by the amount specified in the argument.
`0pt` is the default. Negative value is also acceptable.

## License

Public Domain.
