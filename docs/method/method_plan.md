
The overall approach we recommend is to fit a range of models, where possible, to assess sensitivity.

- Checking the consistency between Admin-1 estimates from the 3 approaches is a good idea. We expect
some shrinkage (attenuation of estimates) with the <a href="../method_unit" style="color: green;">area-level </a> and <a href="../method_unit" style="color: blue;">unit-level models</a>, but this should not be large.
- If there is systematic differences between <a href="../method_unit" style="color: red;">direct estimates</a> and the <a href="../method_unit" style="color: blue;">unit-level model</a> estimates (for example the latter tend to be larger or smaller) then it may mean that the informative sampling is not being accounted for in the <a href="../method_unit" style="color: blue;">unit-level models</a>, and the estimates are less trustworthy.
- **No data areas** cannot produce a <a href="../method_unit" style="color: red;">direct estimate</a>, since information from other areas is not used. The
<a href="../method_unit" style="color: green;">area-level </a> may be fitted with the areas having no data being treated as missing, and imputed from the areas with data. One would not want to pursue this avenue if many areas have no data, but stating a
rule for the level of missingness which may be acceptable is not clear, and a current topic of investigation
in the group.
- **Low information areas** are those that produce either a <a href="../method_unit" style="color: red;">direct estimate</a> of 0 or 1, or a variance estimate that is 0 or close to zero (because the variance formulas break down in the face of sparse data
configurations). The <a href="../method_unit" style="color: red;">direct estimates</a> are effectively not useful in such areas.
- <a href="../method_unit" style="color: blue;">unit-level models</a> can give a valid sampling model in low information areas (unlike the <a href="../method_unit" style="color: red;">direct estimate</a>), but the sparsity of information in these areas will generally lead to large uncertainty in these areas, since they are leaning on information from all other areas, with a particular emphasis on neighbors.