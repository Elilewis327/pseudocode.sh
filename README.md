# Purpose

Large Language Models, or LLMs, have fundamentally altered the way we make software.
The question that has yet to be fully answered is how. 
I believe that engineers should be the ones defining how software is made, not executives,
which is why I am building [pseudocode.sh](https://pseudocode.sh). 

## Premise

`Pseudocode` is a programming language built for the agentic era. 
`Pseudocode` is intended to be written by an LLM or human, reviewed by a human, and then transpiled into a 
traditional language, such as Go, TypeScript, or Rust (To start).

## What Makes Pseudocode different from an .md file?

The difference between `Pseudocode` and the existing methods of using scattered rules files is three fold:
1) `Pseudocode` is a well defined framework.
2) `Pseudocode` has both agentic and deterministic checks for validtiy against the target.
3) `Pseduocode` is a compiled language, and much stricter than plain english.

# How it works

## Project layout:
This is the basic outline of a `Pseudocode` project:

```
|- .git/ # `Pseudocode` should be committed.
|- README.md
|- pseudocode/ # `Pseudocode` content
|-- code/ # `Pseduocode` content which will define your generated content.
|--- main.ps
|--- service.ps
|-- pseudo.ps # Primary `Pseduocode` config file.
|-- checks.ps # Specific checks which are performed at compile time.
|- target/ # The output of your transpiled `Pseudocode`.
|-- main.go
|-- service.go
|-- go.sum
|-- Makefile
|-- ...
```

## A couple of base rules:
1) Every PS file will generate 1 (ONE) at MOST target language files.
2) Every PS project will have a vaild pseudo.ps configuration.


## Workflow:
1) Setup your pseudocode.sh configuration (use the command pseudocode to generate a valid template).
2) Write your project, or import it from a target.
3) Transpile with `pseudocode build`
4) Iterate.
