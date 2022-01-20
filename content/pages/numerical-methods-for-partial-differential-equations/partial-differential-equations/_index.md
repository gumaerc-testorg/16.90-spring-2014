---
content_type: page
parent_title: 'Unit 2: Numerical Methods for Partial Differential Equations'
parent_uid: 125c58ac-6a34-5a7c-bba8-de2d3160cb8b
title: 2.2 Partial Differential Equations
uid: 735249e6-5cf9-7136-d3a6-4f4d3458178c
---

*   [<Pre-requisite Material]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/overview3/1690r-pre-requisite-material3)
*   [2.2.1Conservation Laws in Integral and Differential Form]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations)
*   [2.2.2One-Dimensional Burgers Equation]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-one-dimensional-burgers-equation)
*   [2.2.3Convection]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-convection)
*   [2.2.4Characteristics for One-Dimensional Burgers Equation]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-characteristics-for-one-dimensional-burgers-equation)
*   [2.2.5Diffusion]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-diffusion)
*   [2.2.6Convection-Diffusion]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-convection-diffusion)
*   [2.2.7Linear Elasticity]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-linear-elasticity)
*   [\>One-Dimensional Burgers Equation]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations/partial-differential-equations/1690r-one-dimensional-burgers-equation)

2.2.1 Conservation Laws in Integral and Differential Form
---------------------------------------------------------

[Measurable Outcome 2.1]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO21)

In many engineering applications, the physical system is governed by a set of conservation laws. For example, in gas dynamics, the conservation of mass, momentum, and energy are applied to the gas. These conservation laws are often written in integral form for a fixed physical domain. Suppose we have a fixed two-dimensional physical domain, \\(\\Omega\\), with the boundary of the domain, \\(\\delta \\Omega\\). Then, the canonical conservation equation in **integral** form is

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}}{{\\rm d}t}\\int \_{\\Omega } U\\, dA + \\int \_{\\delta \\Omega } \\vec{F}(U) \\cdot \\vec{n}\\, ds = \\int \_{\\Omega } S(U,t)\\, dA, \\label{equ:conservation}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.1)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(U\\) is the conserved state (e.g., mass, momentum or energy per unit volume or per unit area), \\(\\vec{F}\\) is a vector whose elements are the flux of the conserved state in each direction, \\(\\vec{n}\\) is the outward pointing unit normal on the boundary of the domain, and \\(S\\) is a source term.

This conservation law can be writen as a partial differential equation by applying the divergence theorem which states that,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\int \_{\\delta \\Omega } \\vec{F} \\cdot \\vec{n}\\, ds = \\int \_{\\Omega } \\nabla \\cdot \\vec{F} dA. \\label{equ:divergence}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.2)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Thus, Equation [2.1](javascript: void(0)) becomes,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\frac{{\\rm d}}{{\\rm d}t}\\int \_{\\Omega } U\\, dA + \\int \_{\\delta \\Omega } \\vec{F} \\cdot \\vec{n}\\, ds\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = \\int \_{\\Omega } S\\, dA,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.3)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_{\\Omega } \\frac{\\partial U}{\\partial t} \\, dA + \\int \_{\\Omega } \\nabla \\cdot \\vec{F}\\, dA\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = \\int \_{\\Omega } S\\, dA,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.4)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\int \_{\\Omega } \\left( \\frac{\\partial U}{\\partial t} + \\nabla \\cdot \\vec{F} - S \\right)\\, dA\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = 0.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.5)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Since this last equation must remain valid for any arbitrary domain, \\(\\Omega\\), the integrand must be zero everywhere, or, equivalently,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{\\partial U}{\\partial t} + \\nabla \\cdot \\vec{F} = S. \\label{equ:conservation\_ pde}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.6)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Equations [2.1](javascript: void(0)) and [2.6](javascript: void(0)) are the **integral and differential forms** of the canonical conservation equations. Here, the term **canonical** refers to the equations describing the conservation of an arbitrary quantity U with arbitrary flux and source terms F and S.

The above equation is a partial differential equation (PDE), which is a differential equation that contains unknown multivariable functions (e.g., a function of space and time \\(U(x,t)\\) or a function of multiple spatial coordinates \\(U(\\vec{x})\\)) and their partial derivatives (e.g. derivative to time and derivative to a spatial coordinate). This is in contrast to ODEs, which deal with functions of a single variable (e.g., \\(u(t)\\)) and their derivatives.

Conservation of Mass for a Compressible Fluid
---------------------------------------------

An example of a conservation law is the conservation of mass for a compressible fluid. Let the fluid density be \\(\\rho (x,y,t)\\) and the fluid velocity vector as a function of space and time \\(\\vec{v}(\\vec{x}, t)\\). Then, the conservation of mass for the fluid is,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[\\frac{{\\rm d}}{{\\rm d}t}\\int \_{\\Omega } \\rho \\, dA + \\int \_{\\delta \\Omega } \\left( \\rho \\vec{u} \\right) \\cdot \\vec{n}\\, ds = 0.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.7)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

In terms of the canonical form (i.e., ),

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle U\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = \\rho ,\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.8)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\vec{F}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = \\rho \\vec{u},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.9)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle S\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle = 0.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.10)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The Euler Equations for a Compressible Fluid
--------------------------------------------

Often, multiple conservation laws are of interest. In this case, \\(U\\) is a vector of conserved states. Furthermore, the source \\(S\\) is a vectors, and the flux \\(\\vec{F}\\) is a tensor. The dimension of the flux tensor is \\((\\) the number of conserved states \\(\\times\\) the number of spatial dimension \\()\\). In two spatial dimensions, the flux tensos can be written as \\(\\vec{F} = (F, G)\\), where both \\(F\\) and \\(G\\) are tensors. As an example, the Euler equations for a compressible fluid in two-dimensions are the combination of conservation of mass, \\(x\\)-momentum, \\(y\\)-momentum, and energy. In this case,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[U = \\left(\\begin{array}{c} \\rho \\\\ \\rho u \\\\ \\rho v \\\\ \\rho E\\end{array}\\right) \\qquad F = \\left(\\begin{array}{c} \\rho u \\\\ \\rho u^2 + p \\\\ \\rho u v \\\\ \\rho u H\\end{array}\\right) \\qquad G = \\left(\\begin{array}{c} \\rho v \\\\ \\rho u v \\\\ \\rho v^2 + p \\\\ \\rho v H\\end{array}\\right) \\qquad S = 0,\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.11)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The first row of these vectors represents the conservation of mass (see the previous example for more). The second and third row represent conservation of \\(x\\) and \\(y\\) momentum, respectively. And, the fourth row represents conservation of energy. Note that in addition to the fluid density (\\(\\rho\\)) and the \\(x\\) and \\(y\\) velocity components (\\(u\\) and \\(v\\)), the other quantities in these equations are:

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle p\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\mbox{static pressure},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.12)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle E\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\mbox{total energy},\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.13)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle H\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\mbox{total enthalpy}.\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(2.14)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

The total energy and total enthalpy are related by,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[H = E + \\frac{p}{\\rho }.\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.15)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

This system of equations is not quite complete, however, since the number of equations does not equal the number of dependent variables in the equations. In particular, note that we have given five equations thus far (the four conservation equations and the relationship of \\(H\\) to \\(E\\)) while the number of dependent variables is six (i.e. \\(\\rho\\), \\(u\\), \\(v\\), \\(p\\), \\(E\\), and \\(H\\)). The final equation is an equation of state. Often, we assume an ideal gas and use the ideal gas law. In terms of the dependent variables we have introduced, the ideal gas law can be written as,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[p = (\\gamma -1)\\left\[\\rho E - \\frac{1}{2}\\rho (u^2 + v^2)\\right\], \\label{equ:ideal\_ gas}\\\]
{{< tdclose >}}
{{< tdopen >}}
(2.16)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

where \\(\\gamma\\) is the ratio of specific heats (for air, \\(\\gamma \\approx 1.4\\)). Many of you may be more familiar with the ideal gas law in the form, \\(p = \\rho R T\\) where \\(R\\) is the gas constant and \\(T\\) is the temperature. Equation [2.16](javascript: void(0)) is (in fact) equivalent to \\(p = \\rho R T\\) but Equation [2.16](javascript: void(0)) is used since \\(p = \\rho R T\\) introduces a new dependent variable (i.e. the temperature) and would therefore require yet another state equation to complete the system.

BackPre-requisite Material ContinueOne-Dimensional Burgers Equation