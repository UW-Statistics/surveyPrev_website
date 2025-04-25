After completing the data sparsity check, users can access the **Advanced Options** panel. By clicking to expand it, users can customize model settings such as enabling the nested model or incorporating covariates.

## <span style="color:royalblue">Nested Admin-2 Model</span>

The spatial models we use smooth the raw data both **locally** and **nationally**. **Oversmoothing** is a concern when data are sparse.

Recall that surveys are powered to produce reliable estimates for some indicators at Admin-1 and, hence, we would like to *recover* the weighted estimates, rather than distort away from those.

To prevent overshrinkage at the Admin-1 level, we have developed a **nested** model in which we have

$$
p_c = \text{expit} \left( \alpha_{a[s_c]} + e_{i[s_c]} + S_{i[s_c]} \right),
$$

where $a[s_c]$ is the Admin-1 area within which cluster $c$ with location $s_c$ is contained and the $\alpha_a$ are a set of Admin-1 level fixed effects which are included to effectively recover the weighted estimates.

The $e_{i[s_c]}+S_{i[s_c]}$ terms then smooth **within** each Admin-1 area. This model can be viewed as being consistent with the sampling scheme in which the Admin-1 areas are sampling strata. Currenlty this option only affects unit-level models at or beyond Admin-2 level.

**Default:** Disabled (non-nested)

## <span style="color:royalblue">Covariate Incorporation</span>

Users can incorporate area-level external covariates into both area-level and unit-level models to improve estimation. To do so, first select the desired Admin level. A template `.csv` file can be downloaded, containing the list of regions at the selected admin level. Users should add new column(s) corresponding to the covariates and fill in the covariate values for each region. Once completed, the file should be uploaded back into the app. The covariates are automatically incorporated into the model fitting process after clicing the `apply` button. 

**Default:** No covariates. 
