# StructuredSingularValues.jl

<!--[![Stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://hurak.github.io/StructuredSingularValues.jl/stable)-->
[![Dev](https://img.shields.io/badge/docs-dev-blue.svg)](https://hurak.github.io/StructuredSingularValues.jl/dev)
[![Build Status](https://github.com/hurak/StructuredSingularValues.jl/workflows/CI/badge.svg)](https://github.com/hurak/StructuredSingularValues.jl/actions)
[![Coverage](https://codecov.io/gh/hurak/StructuredSingularValues.jl/branch/master/graph/badge.svg)](https://codecov.io/gh/hurak/StructuredSingularValues.jl)

An (experimental) Julia package for computing the *Structured Singular Value (SSV, also Ī¼)* of a (in general) complex matrix. In fact, just *lower and upper bounds* are computed as the computation of the exact value is known to be NP hard.

## What is *Structured Singular Value* of a matrix?
In order to explain what *structured singular value* is, we need to recall what classical [singular value](https://en.wikipedia.org/wiki/Singular_value) of a matrix is. In particular, we focus on the largest singular value Ļā(M), which plays the role of an operator norm for the matrix M.

Furthermore, we need to be able to specify a *structure* of a matrix. Loosely speaking, we just specify which elements in the matrix are zero and which a free to assume real or complex values. For some matrix Ī, we say that if it has the given structure, it belong to some set š«, that is, Īāš«.

With the concept of a singular value and some way to characterize a structure of a matrix, we can define the (largest) structured singular value of a matrix M in the following way

Ī¼(M) = 1/(min {Ļā(Ī): Īāš«, det(I-MĪ)=0}).

Clearly, if the matrix Ī has no structure, the structured singular value Ī¼ of the matrix M is equal to the the reciprocal value of the largest singular value Ļā(Ī) of some smallest (in the sense of Ļā) matrix Ī that makes the determinant of I-MĪ vanish. But this is exactly equal to the standard (largest) singular value Ļā(M). That is, in this unstructured case Ī¼(M)=Ļā(M). In presence of some structure imposed on Ī, Ī¼(M)ā¦Ļā(M).


## Usage of the `StructuredSingularValues.jl` package
...

## Anticipated use in analysis of robust stability of LTI systems
An anticipated use of this computation is in analysis of robustness of linear time invariant (LTI) dynamical systems. If such a system is modelled by a (matrix) transfer function M(s), structured singular value(s) are computed for a grid of frequencies Ļā, k=1,ā¦,N, at which the transfer function M(s) evaluates to M(jĻā). This evaluation of the matrix M(s) at a grid of points along the imaginary axis and subsequent computation of the SSV is left for the user. In this package we only aim at computing the SSV for a given (constant) matrix.

## References
1. Doyle, John. āAnalysis of Feedback Systems with Structured Uncertainties.ā IEE Proceedings D (Control Theory and Applications) 129, no. 6 (November 1, 1982): 242ā50. https://doi.org/10.1049/ip-d.1982.0053.
2. Packard, Andrew, Pete Seiler, and Gary Balas. āStructured Singular Value and Applications: Analyzing the Effect of Linear Time-Invariant Uncertainty in Linear Systems.ā In Encyclopedia of Systems and Control, edited by John Baillieul and Tariq Samad, 1ā8. London: Springer, 2013. https://doi.org/10.1007/978-1-4471-5102-9_163-1.
3. Roos, C., and J. -M. Biannic. āA Detailed Comparative Analysis of All Practical Algorithms to Compute Lower Bounds on the Structured Singular Value.ā Control Engineering Practice 44 (November 1, 2015): 219ā30. https://doi.org/10.1016/j.conengprac.2015.06.006.
4. Young, Peter M., Matthew P. Newlin, and John C. Doyle. āComputing Bounds for the Mixed Ī¼ Problem.ā International Journal of Robust and Nonlinear Control 5, no. 6 (1995): 573ā90. https://doi.org/10.1002/rnc.4590050604.
5. Young, Peter M., Matthew P. Newlin, and John C. Doyle. āPractical Computation of the Mixed Ī¼ Problem.ā In 1992 American Control Conference, 2190ā94, 1992. https://doi.org/10.23919/ACC.1992.4792521.
6. Young, P.M., and J.C. Doyle. āA Lower Bound for the Mixed /Spl Mu/ Problem.ā IEEE Transactions on Automatic Control 42, no. 1 (January 1997): 123ā28. https://doi.org/10.1109/9.553696.
7. Young, Peter M., and John C. Doyle. āComputation of Mu with Real and Complex Uncertainties.ā In 29th IEEE Conference on Decision and Control, 1230ā35 vol.3, 1990. https://doi.org/10.1109/CDC.1990.203804.
