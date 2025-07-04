
# halzu2

A LaTeX package for typesetting "split annotation" (Halzu, 할주, 割註, Warichu),
a traditional CJK typographic convention of typesetting various notes in small
double lines. It is (or was) frequently used, among others, in law books.

## Usage

In preamble:
```latex
\usepackage{halzu2}
```
and in the body of document:
```latex
\halzu{...}
\halzu*{...}
\halzu[c|r|j]{...}
```
The starred version will make the contents of the Halzu box center-aligned.

Optional argument `[c]`, `[r]`, or `[j]` denotes
ceter-aligned, ragged-right, or justified alignment, respectively.

## Optional commands

```latex
\def\halzuraise{0pt}
```
makes all Halzu boxes move upwards by the amount specified.
`0pt` is the default. Negative value is also acceptable.

```latex
\def\halzusize{0.7}
```
denotes the factor between the current document font size and the Halzu font size.
The default value is `0.7`, the same as `scriptsize`.

```latex
\def\halzuopening{(}
\def\halzuclosing{)}
```
These commands define surrounding characters that will be typeset at
the beginning and ending of Halzu box. Ascii parentheses are default.
Empty values are also acceptable.

```latex
\halzucentering
\halzuraggedright
\halzujustify
```
These commands make the contents of all Halzu boxes thereafter
center-aligned or ragged-right or justified, respectively.
The last one, `\halzujustify` is the default value.

```latex
\newfontfamily\halzufont{Noto Sans CJK KR Light}[Script=Hangul, Language=Korean]
```
declares the font (using fontspec package in the above example)
that will be used in the contents of all the Halzu boxes.
Default value is the document font.

## Example

```latex
\documentclass[a5paper,12pt]{article}
\usepackage[hangul]{kotex}
\setmainfont{Noto Sans CJK KR}
[
  Renderer=OpenType,
  Script=Hangul, Language=Korean,
  CompressPunctuations, RemoveClassicSpaces,
]
\usepackage{halzu2, iftex}
\def\halzuopening{\hskip\smallskipamount}
\let\halzuclosing\halzuopening
\def\halzusize{0.6}
\typesetclassic
\ifxetex \removeclassicspaces \fi
\begin{document}
\section*{\huge 經國大典}
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

## Caveat

*halzu2* does not support `\parshape` paragraph,
with the exception of LaTeX's `list` environment
such as `itemize` `enumerate` `description` `quote` or `verse`.

## License

Public Domain.
