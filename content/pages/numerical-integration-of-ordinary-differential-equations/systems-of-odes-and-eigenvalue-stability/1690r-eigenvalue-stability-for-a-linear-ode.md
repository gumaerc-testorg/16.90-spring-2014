---
content_type: page
parent_title: 1.6 Systems of ODE's and Eigenvalue Stability
parent_uid: 36e637ce-d6ff-e05d-3606-0d537611ad2e
title: 1.6 Systems of ODE's and Eigenvalue Stability
uid: 04ce95ca-3b3a-cc38-5d83-81923a3dd6fe
---

*   [<Linear Constant Coefficient Systems]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/systems-of-odes-and-eigenvalue-stability/1690r-linear-constant-coefficient-systems)
*   [1.6.1Nonlinear Systems]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/systems-of-odes-and-eigenvalue-stability)
*   [1.6.2Linear Constant Coefficient Systems]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/systems-of-odes-and-eigenvalue-stability/1690r-linear-constant-coefficient-systems)
*   [1.6.3Eigenvalue Stability for a Linear ODE]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/systems-of-odes-and-eigenvalue-stability/1690r-eigenvalue-stability-for-a-linear-ode)
*   [1.6.4Imaginary Eigenvalues]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/systems-of-odes-and-eigenvalue-stability/1690r-imaginary-eigenvalues)
*   [\>Imaginary Eigenvalues]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/systems-of-odes-and-eigenvalue-stability/1690r-imaginary-eigenvalues)

1.6.3 Eigenvalue Stability for a Linear ODE
-------------------------------------------

[Measurable Outcome 1.2]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO12), [Measurable Outcome 1.3]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO13), [Measurable Outcome 1.6]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO16), [Measurable Outcome 1.9]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO19), [Measurable Outcome 1.18]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO118)

As we have seen, while numerical methods can be convergent, they can still exhibit instabilities as \\(n\\) increases for finite \\({\\Delta t}\\). For example, when applying the midpoint method to either the ice particle problem in Section [1.2.4]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/discretizing-odes/1690r-the-forward-euler-method) or the simpler model problem in Example [1.66](javascript: void(0)), instabilities were seen in both cases as \\(n\\) increased. Similarly, for the nonlinear pendulum problem in Example [1.86](javascript: void(0)), the forward Euler method had a growing amplitude again indicating an instability. The key to understanding these results is to analyze the stability for finite \\({\\Delta t}\\). This analysis is different than the stability analysis we performed in Section [1.5.2]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/zero-stability-and-the-dahlquist-equivalence-theorem/1690r-stability) since that analysis was for the limit of \\({\\Delta t}\\rightarrow 0\\).

Suppose we are interested in solving the linear ODE,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[u\_ t = \\lambda u.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.99)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Consider the Forward Euler method applied to this problem,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n+1} = v^ n + \\lambda {\\Delta t}v^ n. \\label{equ:fe\_ lin}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.100)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Similar to the zero stability analysis, we will assume that the solution has the following form,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[v^{n} = g^ n v^0, \\label{equ:gdef}\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.101)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(g\\) is the amplification factor (and the superscript \\(n\\) acting on \\(g\\) is again raising to a power). As in the zero stability analysis, we wish to determine under what conditions \\(|g| > 1\\) since this would mean that \\(v^ n\\) will grow unbounded as \\(n \\rightarrow \\infty\\). Substituting Equation [1.101](javascript: void(0)) into Equation [1.100](javascript: void(0)) gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[g^{n+1} = (1 + \\lambda {\\Delta t})g^ n.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.102)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the only non-zero root of this equation gives,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[g = 1 + \\lambda {\\Delta t},\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.103)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

which is the amplification factor for the forward Euler method. Now, we must determine what values of \\(\\lambda {\\Delta t}\\) lead to instability (or stability). A simple way to do this for multi-step methods is to solve for the stability boundary for which \\(|g| = 1\\). To do this, let \\(g = e^{i\\theta }\\) (since \\(|e^{i\\theta }| = 1\\)) where \\(\\theta = \[0,2\\pi \]\\). Making this substitution into the amplification factor,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[e^{i\\theta } = 1 + \\lambda {\\Delta t}\\quad \\Rightarrow \\quad \\lambda {\\Delta t}= e^{i\\theta } - 1.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.104)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, the stability boundary for the forward Euler method lies on a circle of radius one centered at -1 along the real axis and is shown in Figure [1.10]({{< baseurl >}}/resources/fe_stab).

![This graph demonstrates the stability boundary for the forward Euler method, which lies on a circle of radius one centered at -1 along the real axis.]({{< resource_file ffa99b42-f438-0a33-20c9-f53791a67819 >}})

**Figure 1.10**: Forward Euler stability region

For a given problem, i.e. with a given \\(\\lambda\\), the timestep must be chosen so that the algorithm remains stable for \\(n \\rightarrow \\infty\\). Let's consider some examples.

Example
-------

Let's return to the previous example, \\(u\_ t = -u^2\\) with \\(u(0) = 1\\). To determine the timestep restrictions, we must estimate the eigenvalue for this problem. Linearizing this problem about a known state gives the eigenvalue as \\(\\lambda = {\\partial f}/{\\partial u} = -2u\\). Since the solution will decay from the initial condition (since \\(u\_ t < 0\\) because \\(-u^2 < 0\\)), the largest magnitude of the eigenvalue occurs at the initial condition when \\(u(0) = 1\\) and thus, \\(\\lambda = -2\\). Since this eigenvalue is a negative real number, the maximum \\({\\Delta t}\\) will occur at the maximum extent of the stability region along the negative real axis. Since this occurs when \\(\\lambda {\\Delta t}= -2\\), this implies that \\({\\Delta t}< 1\\). To test the validity of this analysis, the forward Euler method was run for \\({\\Delta t}= 0.9\\) and \\({\\Delta t}= 1.1\\). The results are shown in Figure [1.11]({{< baseurl >}}/resources/ga_fe_stab) which are stable for \\({\\Delta t}= 0.9\\) but are unstable for \\({\\Delta t}= 1.1\\).

![This figure shows two line graphs of forward Euler solutions used to determine the timestep restrictions, one that shows stability for Δt=0.9 and the other that is unstable for Δt=1.1.]({{< resource_file 9f9bf44b-75d4-cda7-ee12-7e6196a405a1 >}})

**Figure 1.11**: Forward Euler solution for \\(u\_ t = -u^2\\) with \\(u(0) = 1\\) with \\({\\Delta t}= 0.9\\) and \\(1.1\\).

Pendulum Example
----------------

Next, let's consider the application of the forward Euler method to the pendulum problem. For this case, the linearization produces a matrix,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial f}{\\partial u} = \\left(\\begin{array}{cc} 0 & -\\frac{g}{L}\\cos \\theta \\\\ 1 & 0 \\end{array}\\right)\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.105)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The eigenvalues can be found from the roots of the determinant of \\({\\partial f}/{\\partial u} - \\lambda I\\):

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\det \\left(\\frac{\\partial f}{\\partial u} - \\lambda I\\right)\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\det \\left(\\begin{array}{cc} -\\lambda & -\\frac{g}{L}\\cos \\theta \\\\ 1 & -\\lambda \\end{array}\\right)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.106)
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
\\(\\displaystyle \\lambda ^2 + \\frac{g}{L}\\cos \\theta = 0\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.107)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\Rightarrow\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\lambda = \\pm i \\sqrt {\\frac{g}{L}\\cos \\theta }\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.108)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, we see that the eigenvalues will always be imaginary for this problem. As a result, since the forward Euler stability region does not contain any part of the imaginary axis (except the origin), no finite timestep exists which will be stable. This explains why the amplitude increases for the pendulum simulations in Figure [1.8]({{< baseurl >}}/resources/nonpen_fe-1).

BackLinear Constant Coefficient Systems ContinueImaginary Eigenvalues