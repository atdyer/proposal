# Notes and sources for formal methods

## Literature Review

### Verification and Validation of Simulations Against Holism

**Author.**

Jebeile and Ardourel

**Abstract**

It has been argued that the Duhem problem is renewed with computational models since model assumptions having a representational aim and computational assumptions cannot be tested in isolation. In particular, while the Verification and Validation methodology is supposed to prevent such holism, Winsberg (Philos Compass 4:835–845, 2009; Science in the age of computer simulation, University of Chicago Press, Chicago, 2010) argues that verification and validation cannot be separated in practice. Morrison (Reconstructing reality: models, mathematics, and simulations, Oxford University Press, Oxford, 2015) replies that Winsberg overstates the entanglement between the steps. The paper aims at arbitrating these two positions, by stressing their respective validity in relation to domains of application. It importantly argues for an increasing use of formal methods in verification, that makes disentanglement possible.

**Notes.**

This paper first describes verification and validation:

* **Verification**: Aims to quantify the shift between the computer code and the conceptual part of the model of which the code is implemented.
  * **Code Verification**: Justify that the code is appropriately implemented within the hardware (i.e., architecture, memory and operating system of the computer) and system software, that all its functions work and that it will not yield wrong predictions for mere computer software reasons (e.g., algorithm error, bug, convergence problem or problem of existence and uniqueness of solutions).
  * **Solution Verification**: Assess whether the solutions obtained by the simulation are consisten with model assumptions; in other words, whether they are good approximate solutions to the equations.
* **Validation**: Comparing a target set of numerical results with experimental measurements or other validated codes. 

This paper then arbitrates two positions taken on verification and validation: 

* Winsberg argues that the two are entangled because scientists do not succeed in providing strong arguments establishing that the results of the simulation approximate the exact solutions to the original equations during the verification step. Numerical errors can thus be entangled with pure modeling errors. "what simulationists are forced to do is to focus... on establishing that the combined effect of the models they begin with, and the computational methods they employ, provide results that are reliable enough for the purposes to which they intend to put them." These methods, though, fail to provide grounds that the computer program correctly provides solutions to the original equations. 
* Morrison argues that Winsberg overstates this entanglement.

The author argues for formal methods: "We now argue that formal methods are a recent and promising method for ensuring that there is no uncontrollable numerical errors in a computational model, a method that may well apply to more and more scientific domains. Formal methods in verification have not yet been explored in philosophy of science, and yet constitute serious attempts at overcoming holism."

The second statement is in agreement with our stance on the role of formal methods in scientific computing; we argue for a separation of concerns---scientific software is the sum of interstitial machinery and the underlying numerics. The first statement, however, seems to argue for the application of formal methods to the numerical portion of software as a method of controlling numerical errors, for *solution verification*. Our argument is for the application of formal methods to the machinery of scientific software, i.e. *code verification*.

The author concludes, after providing examples, that there is a spectrum of entanglement of V&V, and each domain of interest falls somewhere on that spectrum. They argue that whether a domain of interest is critical, e.g. to public safety, is a major factor in determining where that system falls on the spectrum. Our stance is that, while that is often currently the case, the advent of lightweight tools such as Alloy is changing the outlook. The scientific method demands verification and reproducibility, and so scientific research that makes use of software must be able to provide strong arguments for the verification of that software with respect to the mathematical equations it represents. Lightweight formal methods are capable of making these arguments in the context of code verification, a domain that is notoriously lacking this type of argument.

**Quotes.**

A standard definition states that “verification [is] the process of determining that a model implementation accurately represents the developer’s conceptual description of the model and the solution to the model” while validation is defined as “the process of determining the degree to which a model is an accurate representation of the real world from the perspective of the intended uses of the model” (Oberkampf and Trucano 2002, p. 14).

“when a computational model fails to account for real data, we do not know whether to blame the underlying model or to blame the modeling assumptions used to transform the underlying model into a computationally tractable algorithm” (Winsberg 2009, p. 839; 2010, p. 24)

