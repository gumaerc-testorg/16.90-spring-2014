---
content_type: page
parent_title: 2.2 Partial Differential Equations
parent_uid: 735249e6-5cf9-7136-d3a6-4f4d3458178c
title: 2.2 Partial Differential Equations
uid: 53d47d94-d1a2-5853-95d6-3d7a71ad1144
---

*   [<Partial Differential Equations]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations)
*   [2.2.1Conservation Laws in Integral and Differential Form]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations)
*   [2.2.2One-Dimensional Burgers Equation]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-one-dimensional-burgers-equation)
*   [2.2.3Convection]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-convection)
*   [2.2.4Characteristics for One-Dimensional Burgers Equation]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-characteristics-for-one-dimensional-burgers-equation)
*   [2.2.5Diffusion]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-diffusion)
*   [2.2.6Convection-Diffusion]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-convection-diffusion)
*   [2.2.7Linear Elasticity]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-linear-elasticity)
*   [\>Convection]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-convection)

2.2.2 One-Dimensional Burgers' Equation
---------------------------------------

[Measurable Outcome 2.1]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO21), [Measurable Outcome 2.2]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO22) 

Burgers' equation is a fundamental partial differential equation from fluid mechanics. It occurs in various areas, such as modeling of gas dynamics and traffic flow. It is named for Johannes Martinus Burgers (1895-1981). The one-dimensional Burgers' equation is given in differential form as:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial u}{\\partial t} + u \\frac{\\partial u}{\\partial x} = 0 \\label{equ:burgers}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.17)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp; \\(U=u, \\vec{F}=u\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(U=u, \\vec{F}=u^2\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; \\(U=\\frac{1}{2}u, \\vec{F}=u^2\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp; \\(U=u,\\vec{F}=\\frac{1}{2}u^2\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Answer: This solution can be verified by plugging in \\(\\vec{F} =\\frac{1}{2} u^2\\) and noting that \\(\\frac{\\partial \\vec{f}}{\\partial x} = \\frac{\\partial \\vec{F}}{\\partial u}\\frac{\\partial u}{\\partial x}\\) and we arrive that the above differential form.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

BackPartial Differential Equations ContinueConvection