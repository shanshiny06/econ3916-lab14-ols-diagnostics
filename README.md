# econ3916-lab14-ols-diagnostics
# OLS Diagnostics: When the Standard Error Is Lying

## Objective

I tested when ordinary least squares standard errors can be trusted, and what
changes when I use robust (HC3) standard errors, check residual diagnostics,
and look at the influence of individual rows.

## Methodology

- Simulated data where the spread of the errors grows with x, then fitted one
  regression and computed both classical and HC3 standard errors for the slope.
- Repeated the simulation across 400 samples and recorded how often each 95%
  confidence interval covered the true slope, along with the Monte Carlo
  standard error of each coverage rate.
- Made four residual plots and read them alongside Breusch-Pagan (constant
  variance) and Jarque-Bera (normality) tests.
- Deleted a single row from a 600-row dataset and measured how far the slope
  and its standard error moved.
- Fitted a regression on the California Housing data and compared the HC3 and
  classical standard errors on AveRooms.
- Wrote my own function, `hc3_se()`, and used it to compute the HC3 standard
  error on AveRooms with all districts and again without the 965 districts at
  the 5.0 ceiling.
- *(Extension)* Computed Cook's distance and measured how much of the total
  came from the five most influential districts.
- *(Take-home Challenge)* Built a regression that passed every diagnostic and
  was still wrong.

## Key Findings

- **Same slope, different uncertainty.** On the simulated data, both methods
  gave the same slope, [YOUR VALUE]. The classical standard error was
  [YOUR VALUE] and the HC3 standard error was [YOUR VALUE].
- **Coverage across 400 samples.** The classical 95% interval covered the true
  slope in [YOUR VALUE] of samples (Monte Carlo SE [YOUR VALUE]). The HC3
  interval covered it in [YOUR VALUE] (Monte Carlo SE [YOUR VALUE]).
- **Diagnostics.** I read the four residual plots together with the
  Breusch-Pagan and Jarque-Bera results rather than relying on any one of them
  alone.
- **One row out of 600.** Deleting a single row moved the slope by
  [YOUR VALUE] of its own standard error, and the standard error fell by
  [YOUR VALUE].
- **California Housing.** The HC3 standard error on AveRooms was [YOUR VALUE]
  times the classical one.
- **Censored districts.** With my `hc3_se()` function, the HC3 standard error
  on AveRooms was [YOUR VALUE] with all districts and [YOUR VALUE] after
  removing the 965 districts at the 5.0 ceiling.
- *(Extension)* Five districts carried [YOUR VALUE] of the total Cook's
  distance.
- *(Take-home Challenge)* [YOUR RESULT]
