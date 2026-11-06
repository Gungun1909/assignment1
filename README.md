# Logic Lab: Boolean Workbench

A dependency-free browser tool for simplifying and simulating 4-6 variable Boolean functions.

## Run

Open `index.html` in a browser. The local simplifier and simulator do not need a server, package installation, or API key.

## Use

1. Enter an expression using variables `A` through `F`, select the variable count, and optionally enter comma-separated don't-care minterms.
2. Select SOP or POS to view its Karnaugh maps, algebraic merge identities, and simulate that gate network. The truth table compares the original function with the selected simplified circuit.
3. Optionally configure an OpenAI-compatible chat-completions endpoint, model, and API key, then request a GenAI review. Its proposed forms are checked against every defined truth-table row; local exact minimization remains the reference.

Supported operators are postfix `'`, prefix `!` or `~` for NOT; `&`, `*`, `.`, or adjacency for AND; `+` or `|` for OR; and `^` for XOR. Parentheses, constants `0` and `1`, and assignment prefixes such as `F =` are supported.

The exact local minimizer uses Quine-McCluskey prime implicants with an exact cover search. Don't-care rows are excluded from equivalence checks and may be used in groups. The optional AI request sends the minterm sets and local forms directly to the configured endpoint; the API key is held only in the page and is not persisted.