Run
From this folder, open the desktop interface with:

py gui.py
The interface lets you enter a phrase or choose an example, analyze it with the button or Ctrl+Enter, and inspect the parser result, plain-language interpretation (for accepted phrases), and token table. It uses Tkinter, which is included with most Python desktop installations.

To use the original command-line interface instead, run:

py main.py
The program reads example sentences from test_cases.txt, prints their tokens, and reports whether each sentence matches this grammar:

S  -> NP VP
S  -> NP VP CONJ S
NP -> NOUN | PRON | PRON NOUN | DET NOUN | DET ADJ NOUN | ADJ NOUN | SLANG NOUN
VP -> VERB NP | VERB NP PP | VERB NP PP PP | AUX VERB NP
PP -> PREP NP
Keywords are matched case-insensitively. Unknown words are reported as WORD, while punctuation and other invalid characters are preserved and rejected by the parser instead of being silently ignored.

The program first analyzes the examples in test_cases.txt, then opens an interactive prompt. Enter a phrase after Phrase> and type q to quit. For accepted phrases, it also displays a simple plain-language English interpretation.