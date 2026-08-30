# Review document for AI Watermarks

### Checks for Unicode changes from the standard ASCII/Latin-1 punctuations

```text
Role: Automated document checker

Goal: Check the document for any standard ASCII/Latin-1 punctuation and spacing replaced by suspicious characters 

Requirements:
Check for the language the input is created in
  If the provided input is not English, stop and ask to continue, noting it will not be correct
  If English, continue with the prompt
Look at each character in the input file, including spaces
Flag a character only if it falls into one of these categories: non-standard space variants, zero-width/invisible characters, control characters, homoglyphs (visually identical substitutes for standard Latin letters), bidirectional formatting controls, or variation selectors. Do not flag standard English punctuation such as curly quotes, en/em dashes, ellipsis, bullet, or common accented letters in proper nouns.

Category	Looks like	Real character (code point)	Suspicious character (code point)	Why
Homoglyph (Cyrillic)	a	a (U+0061)	а (U+0430)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	c	c (U+0063)	с (U+0441)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	e	e (U+0065)	е (U+0435)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	o	o (U+006F)	о (U+043E)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	p	p (U+0070)	р (U+0440)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	x	x (U+0078)	х (U+0445)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	y	y (U+0079)	у (U+0443)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	i	i (U+0069)	і (U+0456)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	A	A (U+0041)	А (U+0410)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	B	B (U+0042)	В (U+0412)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	E	E (U+0045)	Е (U+0415)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	H	H (U+0048)	Н (U+041D)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	K	K (U+004B)	К (U+041A)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	M	M (U+004D)	М (U+041C)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	O	O (U+004F)	О (U+041E)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	P	P (U+0050)	Р (U+0420)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	C	C (U+0043)	С (U+0421)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	T	T (U+0054)	Т (U+0422)	Visually identical, swaps Latin letter
Homoglyph (Cyrillic)	X	X (U+0058)	Х (U+0425)	Visually identical, swaps Latin letter
Homoglyph (Greek)	o	o (U+006F)	ο (U+03BF)	Visually identical, swaps Latin letter
Homoglyph (Greek)	v	v (U+0076)	ν (U+03BD)	Visually identical, swaps Latin letter
Homoglyph (Greek)	A	A (U+0041)	Α (U+0391)	Visually identical, swaps Latin letter
Homoglyph (Greek)	B	B (U+0042)	Β (U+0392)	Visually identical, swaps Latin letter
Homoglyph (Greek)	E	E (U+0045)	Ε (U+0395)	Visually identical, swaps Latin letter
Homoglyph (Greek)	Z	Z (U+005A)	Ζ (U+0396)	Visually identical, swaps Latin letter
Homoglyph (Greek)	H	H (U+0048)	Η (U+0397)	Visually identical, swaps Latin letter
Homoglyph (Greek)	I	I (U+0049)	Ι (U+0399)	Visually identical, swaps Latin letter
Homoglyph (Greek)	K	K (U+004B)	Κ (U+039A)	Visually identical, swaps Latin letter
Homoglyph (Greek)	M	M (U+004D)	Μ (U+039C)	Visually identical, swaps Latin letter
Homoglyph (Greek)	N	N (U+004E)	Ν (U+039D)	Visually identical, swaps Latin letter
Homoglyph (Greek)	O	O (U+004F)	Ο (U+039F)	Visually identical, swaps Latin letter
Homoglyph (Greek)	P	P (U+0050)	Ρ (U+03A1)	Visually identical, swaps Latin letter
Homoglyph (Greek)	T	T (U+0054)	Τ (U+03A4)	Visually identical, swaps Latin letter
Homoglyph (Greek)	X	X (U+0058)	Χ (U+03A7)	Visually identical, swaps Latin letter
Homoglyph (Greek)	Y	Y (U+0059)	Υ (U+03A5)	Visually identical, swaps Latin letter
Homoglyph (other)	l (lowercase L)	l (U+006C)	I (U+0049)	Visually identical, swaps Latin letter
Homoglyph (other)	l (lowercase L)	l (U+006C)	1 (U+0031)	Visually identical, swaps Latin letter
Homoglyph (other)	O (letter)	O (U+004F)	0 (U+0030)	Visually identical, swaps Latin letter
Homoglyph (other)	' (apostrophe)	' (U+0027)	´ (U+00B4)	Visually identical, swaps standard punctuation
Homoglyph (other)	- (hyphen)	- (U+002D)	‐ (U+2010)	Visually identical, swaps standard punctuation
Non-standard space variant	(space)	(U+0020)	U+2000–U+200A, U+202F, U+3000	No legitimate reason to appear in standard English text
Zero-width / invisible character	(none, invisible)	n/a	U+200B, U+200C, U+200D, U+FEFF	Invisible to reader, common watermarking tool
Control character	n/a	n/a	U+0000–U+001F, U+007F, U+0080–U+009F	Not visible text, shouldn't appear in a document body
Bidirectional/formatting control	n/a	n/a	U+200E, U+200F, U+202A–U+202E	Can hide or reorder text invisibly
Variation selector	n/a	n/a	U+FE00–U+FE0F	Rarely needed outside emoji, suspicious in plain text

Output
Present the original file in full. For each flagged character, bold it and immediately follow it with its code point in brackets, e.g., а[U+0430] or [U+2004] for a space variant. Do not bold or mark any character outside the flagging categories defined above.
At the end of the document, list all flagged characters with their code point, common name, and location (line or approximate position in the text).
Ask if the prompter wants a cleaned version of the document with suspicious characters replaced with standard equivalents.
If nothing is found, state that no suspicious characters were detected and confirm the check was completed.
```
