---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 1.9 Runge-Kutta Methods
parent_type: CourseSection
parent_uid: c5e7e539-a82c-8e62-0c8a-e738a18f6f10
title: 1.9 Runge-Kutta Methods
uid: 1f5a4263-b1f3-f522-02d6-af00f58ae206
---

*   [\<Four-Stage Runge-Kutta Method]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods/1690r-four-stage-runge-kutta-method)
*   [1.9.1Two-Stage Runge-Kutta Methods]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods)
*   [1.9.2Four-Stage Runge-Kutta Method]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods/1690r-four-stage-runge-kutta-method)
*   [1.9.3Stability Regions]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods/1690r-stability-regions)
*   [\>Numerical Methods for Partial Differential Equations]({{< baseurl >}}/pages/numerical-methods-for-partial-differential-equations)

1.9.3 Stability Regions
-----------------------

[Measurable Outcome 1.16]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO116), [Measurable Outcome 1.18]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO118), [Measurable Outcome 1.19]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO119)

The eigenvalue stability regions for Runge-Kutta methods can be found using essentially the same approach as for multi-step methods. Specifically, we consider a linear problem in which \\(f = \\lambda u\\) where \\(\\lambda\\) is a constant. Then, we determine the amplification factor \\(g = g(\\lambda {\\Delta t})\\). For example, let's look at the modified Euler method,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle a\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}\\lambda v^ n\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.150)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle b\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}\\lambda \\left(v^ n + {\\Delta t}\\lambda v^ n/2\\right)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.151)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^{n+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^ n + {\\Delta t}\\lambda \\left(v^ n + {\\Delta t}\\lambda v^ n/2\\right)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.152)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle v^{n+1}\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\left\[1 + {\\Delta t}\\lambda + \\frac{1}{2}({\\Delta t}\\lambda )^2 \\right\]v^ n\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.153)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle \\Rightarrow g\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle 1 + \\lambda {\\Delta t}+ \\frac{1}{2}(\\lambda {\\Delta t})^2\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.154)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

A similar derivation for the four-stage scheme shows that,

{{< tableopen >}}
{{< tropen >}}
{{< tdopen >}}
\\\[g = 1 + \\lambda {\\Delta t}+ \\frac{1}{2}(\\lambda {\\Delta t})^2 + \\frac{1}{6}(\\lambda {\\Delta t})^3 + \\frac{1}{24}(\\lambda {\\Delta t})^4.\\\]
{{< tdclose >}}
{{< tdopen >}}
(1.155)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

When analyzing multi-step methods, the next step would be to determine the locations in the \\(\\lambda {\\Delta t}\\)-plane of the stability boundary (i.e. where \\(|g|=1\\)). This however is not easy for Runge-Kutta methods and would require the solution of a higher-order polynomial for the roots. Instead, the most common approach is to simply rely on a contour plotter in which the \\(\\lambda {\\Delta t}\\)-plane is discretized into a finite set of points and \\(|g|\\) is evaluated at these points. Then, the \\(|g|=1\\) contour can be plotted. The following is the MATLAB{{< sup "®" >}} code which produces the stability region for the second-order Runge-Kutta methods (note: \\(g(\\lambda {\\Delta t})\\) is the same for both second-order methods):

```
% Specify x range and number of points
x0 = -3;
x1 =  3;
Nx = 301;

% Specify y range and number of points
y0 = -3;
y1 =  3;
Ny = 301;

% Construct mesh
xv    = linspace(x0,x1,Nx);
yv    = linspace(y0,y1,Ny);
\[x,y\] = meshgrid(xv,yv);

% Calculate z
z = x + i\*y;

% 2nd order Runge-Kutta growth factor
g = 1 + z + 0.5\*z.^2;

% Calculate magnitude of g
gmag = abs(g);

% Plot contours of gmag
contour(x,y,gmag,\[1 1\],'k-');
axis(\[x0,x1,y0,y1\]);
axis('square');
xlabel('Real \\lambda\\Delta t');
ylabel('Imag \\lambda\\Delta t');
grid on;

```

The plots of the stability regions for the second and fourth-order Runge-Kutta algorithms is shown in Figure [1.25]({{< baseurl >}}/resources/rkstab). These stability regions are larger than those of multi-step methods. In particular, the stability regions of the multi-stage schemes grow with increasing accuracy while the stability regions of multi-step methods decrease with increasing accuracy.

![The graph shows the smaller stability boundary for second-order Runge-Kutta algorithm, which is completely within the larger boundary of fourth-order Runge-Kutta algorithms.]({{< resource_file 1d765b08-bf02-2be5-cb59-a6df42ff01bb >}})

**Figure 1.25**: Stability boundaries for second-order and fourth-order Runge-Kutta algorithms (stable within the boundaries).

**Exercise** Consider the Heun method described previously. For a system with real eigenvalues, what is the most negative value of \\(\\lambda {\\Delta t}\\) for which the Heun method will be stable?

Exercise 1

Numerical Response

CheckShow Answer

BackFour-Stage Runge-Kutta Method ContinueNumerical Methods for Partial Differential Equations