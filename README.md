
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
\halzu{...}
\halzu*{...}
```
The starred version will make the contents of Halzu box center-aligned.

## Optional commands

```
\def\halzuraise{0pt}
```
makes all Halzu boxes move upwards by the amount specified.
`0pt` is the default. Negative value is also acceptable.

```
\def\halzusize{0.7}
```
denotes the factor between the current document font size and the Halzu font.
The default value is `0.7`, the same as `scriptsize`.

```
\def\halzuopening{(}
\def\halzuclosing{)}
```
These commands define surrounding characters that will be typeset at
the beginning and ending of Halzu box. Ascii parentheses are default.
Empty values are also acceptable.

```
\halzuonebyonetrue
\halzuonebyonefalse
```
If `true`, Halzu commands will be processed sequentially---one at this
compile round, another at next.  Default is `false`.

## Example

```
\documentclass[a4paper,12pt]{article}
\usepackage[hangul]{kotex}
\setmainfont{Source Han Sans K}[UprightFont=* Normal,BoldFont=* Bold]
\usepackage{halzu}
\def\halzuopening{\hskip.125em}
\let\halzuclosing\halzuopening
\def\halzusize{0.6}
\begin{document}
\section*{\huge 經國大典}
\Large \japanese \endlinechar-1
【田宅】凡訟田宅過五年則勿聽
\halzu{盜賣者相訟未決者父母田宅合執者因幷耕永執者賃居永執者不限年
〇告狀而不立訟過五年者亦勿聽奴婢同}
〇過三年陳田許人告耕
\halzu{海澤則限十年}
〇無主田移給他人
\halzu{有軍役者死亡移徙則給遞立者無役人則給田少者
移徙者五年內還則還給執耕者元無田則還給三分之二}
\end{document}
```

## License

Public Domain.
