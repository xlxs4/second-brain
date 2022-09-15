# Franklin.jl Notes

### Modifications

- header/footer/general look: `src/_css/` and `src/_html_parts`
  
- To customize single chunk, wrap in `@@divname ... @@`, e.g. `@@mybluebackground ... @@`
  

### Code

- `@def hascode = true` for syntax highlighting by [highlight.js](https://highlightjs.org/)
  
- Can "store" code blocks:
  
  \`\`\`julia:./code/example
  
  ```julia
  using LinearAlgebra
  a = [1, 2, 3, 3, 4, 5, 2, 2]
  @show dot(a, a)
  println(dot(a, a)) # hide
  ```
  
  \`\`\`
  
  and then call with (lines with `# hide` are hidden):
  
  `\output{./code/example}`
  
  To not have a code block execute multiple times because it's slow or from a different language, use `\input{julia}{/_assets/scripts/helloo.jl}` which can still be written to file using `scripts/generate_results.jl`. The results can also be input: `\output{/_assets/scripts/helloo.jl}`
  
  Using the latter approach with `generate_results.jl` is preferred because it ensures all of the code in the website works and that all results match the code which makes maintenance easier
  
- for plain text without highlighting, use \`\`\`plaintext ... \`\`\`. Without a language specifier, the default behavior is to go with Julia syntax highlighting
  
- more fancy highlihting:
  
  \`\`\`julia-repl
  
  (v1.4) pkg> add Franklin
  
  shell> blah
  
  julia> 1+1
  
  (Sandbox) pkg> resolve
  
  \`\`\`
  

### Symbols

- Can use HTML for symbols, e.g. `&pi;` or use VSCode autocompletion like so: `\pi[TAB]`
  

### References

- `[^name]`
  

### Misc

- Force line break: `//`
  
- Relative links, e.g. `[my article](/articles/my-article/)`
  
- Table of contents: `\toc`
  
- tag support: page with tag "syntax": `[syntax](/tag/syntax/)`
  

### $\LaTeX$

- `\newcommand`
  
- `\eqref`, `\cite`, etc. Example: `\citep{bezanson17, noether15}`,
  
  - `\biblabel{bezanson17}{Bezanson et al. (2017)} **Bezanson**, **Edelman**, **Karpinski** and **Shah**, [Julia: a fresh approach to numerical computing](https://julialang.org/research/julia-fresh-approach-BEKS.pdf), SIAM review 2017.`
    
  - `\biblabel{noether15}{Noether (1915)} **Noether**,  Körper und Systeme rationaler Funktionen, 1915.`
    
  - `\label{a cool label}` with `\eqref{a cool label}`, for math
    

### File header

```
+++
title = "Code blocks"
hascode = true
date = Date(2019, 3, 22)
rss = "A short description of the page which would serve as **blurb** in a `RSS` feed; you can use basic markdown here but the whole description string must be a single line (not a multiline string). Like this one for instance. Keep in mind that styling is minimal in RSS so for instance don't expect maths or fancy styling to work; images should be ok though: ![](https://upload.wikimedia.org/wikipedia/en/3/32/Rick_and_Morty_opening_credits.jpeg)"
rss_title = "More goodies"
rss_pubdate = Date(2019, 5, 1)

tags = ["syntax", "code"]
+++
```