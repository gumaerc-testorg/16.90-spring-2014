---
content_type: page
parent_title: 1.9 Runge-Kutta Methods
parent_uid: c5e7e539-a82c-8e62-0c8a-e738a18f6f10
title: 1.9 Runge-Kutta Methods
uid: d5200dfd-d11c-9d13-8626-a6b253c602ff
---

*   [<Runge-Kutta Methods]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods)
*   [1.9.1Two-Stage Runge-Kutta Methods]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods)
*   [1.9.2Four-Stage Runge-Kutta Method]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods/1690r-four-stage-runge-kutta-method)
*   [1.9.3Stability Regions]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods/1690r-stability-regions)
*   [\>Stability Regions]({{< baseurl >}}/pages/numerical-integration-of-ordinary-differential-equations/runge-kutta-methods/1690r-stability-regions)

1.9.2 Four-stage Runge-Kutta Method
-----------------------------------

[Measurable Outcome 1.16]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO116), [Measurable Outcome 1.17]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO117), [Measurable Outcome 1.19]({{< baseurl >}}/pages/measurable-outcome-index/#anchorMO119)

The most popular form of a four-stage Runge-Kutta method is:

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
\\(\\displaystyle {\\Delta t}f(v^ n, t^ n)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.145)
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
\\(\\displaystyle {\\Delta t}f(v^ n+a/2, t^ n + {\\Delta t}/2)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.146)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle c\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}f(v^ n+b/2, t^ n + {\\Delta t}/2)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.147)
{{< tdclose >}}

{{< trclose >}}
{{< tropen >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle d\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle =\\)
{{< tdclose >}}
{{< tdopen >}}
\\(\\displaystyle {\\Delta t}f(v^ n+c, t^ n + {\\Delta t})\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.148)
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
\\(\\displaystyle v^ n + \\frac{1}{6}(a + 2b + 2c + d)\\)
{{< tdclose >}}
{{< tdopen >}}
 
{{< tdclose >}}
{{< tdopen >}}
(1.149)
{{< tdclose >}}

{{< trclose >}}

{{< tableclose >}}

Note that this method requires four evaluations of \\(f\\) per iteration. This method is fourth-order accurate, \\(p=4\\).

BackRunge-Kutta Methods ContinueStability Regions