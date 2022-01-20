---
content_type: page
parent_title: 2.7 Eigenvalue Stability of Finite Difference Methods
parent_uid: 935b6a61-8d7d-2772-6ca1-df78ee864834
title: 2.7 Eigenvalue Stability of Finite Difference Methods
uid: cb633bb1-3925-0ab5-7f90-8bb74bb848bb
---

*   [<Circulant Matrices]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/eigenvalue-stability-of-finite-difference-methods/1690r-circulant-matrices)
*   [2.7.1Fourier Analysis of PDEs]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/eigenvalue-stability-of-finite-difference-methods)
*   [2.7.2Matrix Stability for Finite Difference Methods]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/eigenvalue-stability-of-finite-difference-methods/1690r-matrix-stability-for-finite-difference-methods)
*   [2.7.3Circulant Matrices]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/eigenvalue-stability-of-finite-difference-methods/1690r-circulant-matrices)
*   [2.7.4Stability Exercises]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/eigenvalue-stability-of-finite-difference-methods/1690r-stability-exercises)
*   [\>Method of Weighted Residuals]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals)

2.7.4 Stability Exercises
-------------------------

[Measurable Outcome 2.9]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO29), [Measurable Outcome 2.10]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO210), [Measurable Outcome 2.11]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO211)

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; All in the left half plane &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; Two in the left half plane, the rest in a circle in the right half plane &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; Two in the right half plane, the rest in a circle in the right half plane &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; "Along the imaginary axis &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer:

To implement a backward spatial discretization, we modify the matrix A:

for i = 2:Nx-1 A(i,i) = u/dx; A(i,i-1) = -u/dx; end{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Exercise 2
----------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(-\\frac{u}{\\Delta x} -\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) - i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(-\\frac{u}{\\Delta x} +\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) - i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(\\frac{u}{\\Delta x} +\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) + i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(-\\frac{u}{\\Delta x} +\\frac{u}{\\Delta x}\\left\[\\cos \\left(2\\pi \\frac{n}{N}\\right) + i\\sin \\left(2\\pi \\frac{n}{N}\\right)\\right\]\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: We use the formula for the eigenvalues of a circulant matrix with \\(a\_1= -u/\\Delta x\\) and \\(a\_ N = u/ \\Delta x\\).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackCirculant Matrices ContinueMethod of Weighted Residuals