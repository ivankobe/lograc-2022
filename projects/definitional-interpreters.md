# Definitional interpreters for STLC

This file contains 5 projects, depending on which feature X you choose.

## Goals of the project

* Define a (monadic) definitional interpreter for the simply typed
  lambda calculus (STLC) extended with feature(s) X.

* Features X you can choose from (you can also suggest your own):
  1. sum types and algebraic data types
  2. exceptions and state
  3. exceptions and nondeterminism
  4. algebraic effects and effect handlers
  5. natural numbers and primitive recursion, and
     also general recursion (using the delay monad for the latter)

* Define the equational theory for STLC + X. This can take the form
  of a small-step operational semantics (i.e., directed equations).

* Prove that the definitional interpreter is sound (that it validates
  the equational theory).

* A simpler variant of this project will involve defining the
  definitional interpreter into a shallow monad in Agda. A more
  advanced version of this project will involve you using
  [Agda's categories library](https://github.com/agda/agda-categories).

## Suggested background reading materials

A good general reference for different kinds of lambda calculi and
programming language features is Types and Programming Languages
(Pierce) (https://www.cis.upenn.edu/~bcpierce/tapl/).

The definitional interpreter part of the project will take the form of
an interpretation function from well-typed programs into Agda types
(wrapped in a monad if your chosen extensionX involves effects; and
into a suitable category, if using the categories library). For this,
see the lecture notes and exercises on the semantics of propositional
logic, together with the propositions as types correspondence.

### Sum and algebraic data types

* Section 11.9 of Types and Programming Languages (Pierce)
  (https://www.cis.upenn.edu/~bcpierce/tapl/)

  - overview of sum type, its typing rules, and the corresponding
    reduction rules

* Peter Thiemann's slides on Principles of Programming Languages
  https://proglang.informatik.uni-freiburg.de/teaching/konzepte/2018ss/05-types.pdf 

  - a brief overview of algebraic data types

  - in the project we expect you to extend STLC with a type definition
    construct (that extends a special context of type definitions),
    the introduction rule(s) for such algebraic data types, and the
    elimination rule(s) for such algebraic data types

  - for simplicity, in the first instance you can limit your work to
    data types whose constructors' argument types are combinations of
    finite sums and products (over base types and previously defined
    algebraic types); a possible extension is to then also allow the
    argument types to refer to the type being defined (giving you
    inductive types)

### Exceptions and state/nondeterminism

* Notions of Computation and Monads (Moggi)
  (https://www.cs.cmu.edu/~crary/819-f09/Moggi91.pdf)

  - an overview of different kinds of computational effects and
    the monads that naturally model them

  - also gives an overview of the basic programming abstractions
    for effectful programming based on monads

* Combining effects: Sum and tensor (Hyland, Plotkin, Power)
  (https://www.sciencedirect.com/science/article/pii/S0304397506002659)

  - overview of algebraic effects (in the context of this project,
    you can think of them as the canonical operations/equations
    associated with a given notion of computational effect/monad)
  
  - overview of canonical combinations of computational effects and
    monads (in particular, the sum of exceptions and any other effect,
    and the tensor product of state with any other effect/monad)

### Primitive and general recursion

* Gödel’s system T revisited (Alves et al) 
  (https://www.sciencedirect.com/science/article/pii/S0304397509008081?via%3Dihub)

  - Section 2 gives an overview of System T (i.e., simply typed lambda
    calculus extended with natural numbers and primitive recursion)

* Sections 14 and 15 of https://www.cs.bham.ac.uk/~udr/popl/04-19-TLC.pdf

  - an overview of the fixpoint and recursion constructs

* Section 3 of The Delay Monad and Restriction Categories (Uustalu,
  Veltri) (https://pure.itu.dk/ws/files/82292987/ictac17_revised.pdf)

  - an overview of the delay monad (as a coinductive data type)

* Coinduction section of Agda User Manual
  (https://agda.readthedocs.io/en/v2.6.2.1/language/coinduction.html)

  - demonstrates how to define and work with infinite, coinductively
    defined data types in Agda (of which the delay monad is an example)
