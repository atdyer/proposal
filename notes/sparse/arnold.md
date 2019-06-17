# Arnold paper notes and quotes
 
Arguments for full functional verification of sparse matrix codes:

> There are at least two arguments for full functional verification of sparse matrix codes. First, classical static typing is insufficient for static bug detection because these programs contain array indirection, whose memory safety would be typically guaranteed only with run-time safety checks. Dependent type systems may be able to prove memory safety but, in our experience, the necessary dependent-type predicates would need to capture invariants nearly as complex as those that we encountered during full functional verification. For example, to prove full functional correctness, one may need to show that a list is some permutation of a subset of values in another list; to prove memory safety, one may need to show that the values in a list are smaller than the length of another list. It thus seemed to us that with a little extra effort, we can use theorem proving to extend safety to full functional correctness.

1. Static typing is insufficient for static bug detection because of array indirection. 

This is saying that static typing can't help with e.g. array-out-of-bounds errors. So for example in C if your type is int[], the compiler doesn't know how big the array is and so it doesn't limit your array accesses.

In Alloy we can show that operations on sparse matrices preserve the representation invariant and so are memory safe.

2. Synthesis of sparse matrix programs, including the discovery of new formats.

So in order to automatically create a new sparse matrix format, you need an 'arbiter of correctness', something that can tell you whether a format is 'correct'. Synthesis is out of scope for this paper, as well as for us.

---

p.10 for quantifying reuse

> LL provides several built-in functions and combinators for operations over vectors and matrices common in sparse formats.

LL is a shallow embedding in Isabelle/HOL. 

> To quantify rule reuse in our prover, we summarize the reuse of the 24 rules that were needed for proving five sparse formats (see Fig. 10). On average, fewer than 19% of rules used by a particular format are specific to this format, while over 66% of these rules are used by at least three additional formats, a significant level of reuse. Even of the rules needed for more complex formats (CSC and JAD), only up to a third are format-specific.

So the language provides a number of reusable elements, and they show that there is a significant amount of reuse. However, up to a third of the rules used for some of the more complex formats were format specific. Therefore, if a rule doesn't already exist in the language for some other format, it must be created. Creating new language constructs requires a knowledge of lambda calculus.