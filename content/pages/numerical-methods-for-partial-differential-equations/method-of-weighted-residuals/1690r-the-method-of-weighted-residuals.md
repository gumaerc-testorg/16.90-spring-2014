---
content_type: page
parent_title: 2.8 Method of Weighted Residuals
parent_uid: bda18124-71a5-87a7-513f-cb81480a1e18
title: 2.8 Method of Weighted Residuals
uid: 2bb791a5-f105-8421-b20e-147e46034287
---

*   [<The Collocation Method]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals/1690r-the-collocation-method)
*   [2.8.1Functional Approximation of the Solution]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals)
*   [2.8.2The Collocation Method]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals/1690r-the-collocation-method)
*   [2.8.3The Method of Weighted Residuals]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals/1690r-the-method-of-weighted-residuals)
*   [2.8.4Galerkin Method with New Basis]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals/1690r-galerkin-method-with-new-basis)
*   [\>Galerkin Method with New Basis]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/method-of-weighted-residuals/1690r-galerkin-method-with-new-basis)

2.8.3 The Method of Weighted Residuals
--------------------------------------

[Measurable Outcome 2.12]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO212), [Measurable Outcome 2.13]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO213), [Measurable Outcome 2.14]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO214)

While the collocation method enforces the residual to be zero at \\(N\\) points, the method of weighted residuals requires \\(N\\) weighted integrals of the residual to be zero. A weighted residual is simply the integral over the domain of the residual multiplied by a weight function, \\(w(x)\\). For example, in the one-dimensional diffusion problem we are considering, a weighted residual is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{-1}^{1} w(x)\\, R(\\tilde{T},x)\\, dx.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.174)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

By choosing \\(N\\) weight functions, \\(w\_ i(x)\\) for \\(i=1,\\ldots ,N\\), and setting these \\(N\\) weighted residuals to zero, we obtain \\(N\\) equations which we solve to determine the \\(N\\) unknown values of \\(a\_ j\\).

We define the weighted residual for \\(w\_ i(x)\\) to be

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R\_ i(\\tilde{T}) \\equiv \\int \_{-1}^{1} w\_ i(x)\\, R(\\tilde{T},x)\\, dx.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.175)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The method of weighted residuals requires

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[R\_ i(\\tilde{T}) = 0 \\qquad \\mbox{for } i=1,\\ldots ,N.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.176)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In the method of weighted residuals, the next step is to determine appropriate weight functions. A common approach, known as the Galerkin method, is to set the weight functions equal to the functions used to approximate the solution. That is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[w\_ i(x) = \\phi \_ i(x). \\quad \\mbox{(Galerkin)}.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.177)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

For the heat diffusion example we have been considering, this would give weight functions as

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle w\_1(x)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle (1-x)(1+x),\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.178)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle w\_2(x)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle x(1-x)(1+x).\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.179)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Now, we must calculate the weighted residuals. For our example, we have

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R\_1(\\tilde{T})\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_{-1}^{1} w\_1(x)\\, R(\\tilde{T},x)\\, dx,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.180)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_{-1}^{1} (1-x)(1+x)\\, \\left(-2 a\_1 - 6 a\_2 x + 50 e^ x\\right)\\, dx,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.181)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{8}{3} a\_1 + 200 e^{-1}.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.182)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

To do this integral, the following results were used:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_ a^ b (1-x)(1+x)\\, dx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[ x - \\frac{1}{3}x^3 \\right\]\_ a^ b,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.183)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_ a^ b x(1-x)(1+x)\\, dx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[ \\frac{1}{2}x^2 - \\frac{1}{4}x^4 \\right\]\_ a^ b,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.184)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_ a^ b x^2 e^ x\\, dx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[ x^2 e^ x - 2 x e^ x + 2 e^ x \\right\]\_ a^ b.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.185)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Similarly, calculating \\(R\_2\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle R\_2(\\tilde{T})\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_{-1}^{1} w\_2(x)\\, R(\\tilde{T},x)\\, dx,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.186)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_{-1}^{1} x(1-x)(1+x)\\, \\left(-2 a\_1 - 6 a\_2 x + 50 e^ x\\right)\\, dx,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.187)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{8}{5} a\_2 + 100 e^{1} - 700 e^{-1},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.188)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where the following results have been used:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_ a^ b x^2(1-x)(1+x)\\, dx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[ \\frac{1}{3}x^3 - \\frac{1}{5}x^5 \\right\]\_ a^ b,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.189)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_ a^ b x e^ x\\, dx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[ x e^ x - e^ x \\right\]\_ a^ b,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.190)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_ a^ b x^3 e^ x\\, dx\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[ x^3 e^ x - 3 x^2 e^ x + 6x e^ x - 6e^ x \\right\]\_ a^ b.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.191)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Finally, we can solve for \\(a\_1\\) and \\(a\_2\\) by setting the weighted residuals \\(R\_1\\) and \\(R\_2\\) to zero:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{8}{3} a\_1 + 200 e^{-1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.192)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle -\\frac{8}{5} a\_2 + 100 e^{1} - 700 e^{-1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 0.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.193)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This could be written as a \\(2\\times 2\\) matrix equation and solved, but the equations are decoupled and can be readily solved,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\Rightarrow \\left(\\begin{array}{c} a\_1 \\\\ a\_2 \\end{array}\\right) = \\left(\\begin{array}{r} 75 e^{-1} \\\\ \\frac{125}{2}e^{1} - \\frac{875}{2}e^{-1} \\end{array}\\right) = \\left(\\begin{array}{r} 27.591 \\\\ 8.945 \\end{array}\\right).\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.194)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The results using this method of weighted residuals are shown in the figures below. Comparison with the collocation method results shows that the method of weighted residuals is more accurate in this case.

![This graph shows two very similar lines, each with a single peak, that represent the results T and ~T for method of weighted residuals.]({{< resource_file 34c0c178-5219-7294-d452-bc57cac2fbc7 >}})

**Figure 2.30**: Comparison of \\(T\\) (solid) and \\(\\tilde{T}\\) (dashed) for method of weighted residuals.

![This graph has one line, representing the error T minus ~T for method of weighted residuals.  The line begins at the y-axis point zero, then decreases below -0.3, increases above 0.4, then decreases to almost -0.4, and finally increases back to zero.]({{< resource_file 6c3a2597-43d3-b800-8cd3-7d2797bec13b >}})

**Figure 2.31**: Error \\(\\tilde{T}-T\\) for method of weighted residuals.

![This graph of the residual R(~T, x) for method of weighted resiuduals has a single line that steadily decreases and then increases.]({{< resource_file 230e1fbe-722a-155d-36a2-6dc508775fb4 >}})

**Figure 2.32**: Residual \\(R(\\tilde{T},x)\\) for method of weighted residuals.

BackThe Collocation Method ContinueGalerkin Method with New Basis