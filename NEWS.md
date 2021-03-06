# heatwaveR 0.3.5 (2018-11-01)

* Updated one figure in a vignette

# heatwaveR 0.3.5 (2018-10-26)

* `clim_calc()` reinstated to allow for calculation of clims with missing data
* `var` calculations reinstated for documentation issues

# heatwaveR 0.3.5 (2018-10-20)

* `ts2clm()` no longer calls `clim_calc()`, but `clim_calc_cpp()` only 
* `smooth_percentile()` no longer provides option to create variance 
  climatology (the need to no longer create var seemed to not be fully
  implemented in 0.3.4)

# heatwaveR 0.3.4 (2018-10-19)

* `ts2clm()` no longer calculates variance column by default
* `make_whole()` has been deprecated in favour of `make_whole_fast()`

# heatwaveR 0.3.4 (2018-10-17)

* All major functions now produce results only up to the fourth decimal place

# heatwaveR 0.3.4 (2018-10-16)

* Clarified some information on the basic detection vignette
* Corrected a link that went to the wrong page

# heatwaveR 0.3.4 (2018-10-03)

* Changed error handling in `proto_event()` to return no events
  than to stop message with an error.
* This change was picked up by `detect_event()` without any required changes
* `category()` required a bit of cajoling to also output a blank dataframe

# heatwaveR 0.3.4 (2018-10-01)

* Minor tweak to `make_whole_fast()` to provide a cleaner internal output

# heatwaveR 0.3.4 (2018-09-28)

* Removed several unnecessary columns from category climatology output

# heatwaveR 0.3.4 (2018-09-27)

* Fixed bug in `ts2clm()` that prevented calculation of clims with large
  contiguous missing periods of data (e.g. ice coverage).
* Added argument to `category()` that allows one to have the function also 
  output the day-to-day (long) category values, rather than just the
  summary (wide) output.
* Added lon/lat values to documentation for built-in time series

# heatwaveR 0.3.3 (2018-08-23)

* Added CITATION file so that package citation is now set to JOSS article

# heatwaveR 0.3.3 (2018-07-31)

* Added Zenodo DOI badge
* JOSS review process complete
* Added JOSS DOI badge

# heatwaveR 0.3.3 (2018-07-25)

* BUG FIX: corrected issue with `clim_calc_cpp` not being able to calculate
  clims from baselines not beginning and ending on the Julian year by making
  `clim_spread` plug the gaps beforehand with row-wise means.
* Rebuilt pkgdown site to reflect version increase
* v0.3.3 submitted to CRAN

# heatwaveR 0.3.2 (2018-07-23)

* Edits suggested through JOSS review

# heatwaveR 0.3.2 (2018-07-12)

* Remove unneeded copies of data from functions to improve memory-use
  efficiency.

# heatwaveR 0.3.1 (2018-07-10)

* BUG FIX: corrected issue with `make_whole_fast` which did not create a whole,
  complete time series (i.e. missing dates were still present); the missing dates
  caused `clim_calc_cpp` to fail

# heatwaveR 0.3.0 (2018-06-22)

* Re-submitted to CRAN in anticipation of __`ggplot2`__ changes
* `proto_event` now handles all event calculations 'in house'
* This allows `detect_event` to now be given a theoretically limitless number of
  thresholds

# heatwaveR 0.2.7.9003 (2018-06-08)

* Logic catch for `lolli_plot` being asked to highlight more events than are present
* New vignette that looks at calculating more complex climatologies

# heatwaveR 0.2.7.9002 (2018-06-07)

* Tweak to `ts2clm`

# heatwaveR 0.2.7.9001 (2018-06-05)

* Tweaks to `detect_event` and `exceedance`

# heatwaveR 0.2.7.9000 (2018-06-02)

* Unused Rcpp code removed from master branch
* Logo changed slightly
* Codecov back up to 100%
* Addressed one testthat issue that was causing the OSX CRAN build to fail
* Added CRAN link to pkgdown site
* Added Bug Report link to pkgdown site

# heatwaveR 0.2.7 (2018-05-30)

* Accepted on CRAN

# heatwaveR 0.2.7 (2018-05-28)

* Submitted to CRAN

# heatwaveR 0.2.6.9002 (2018-05-25)

* Fixes to `make_whole` and testing
* Fixes to `block_average`
* No longer exporting `make_whole` and `make_whole_fast`
* No longer uses zoo for time series NA handling--made custom function to replace it
* Additional speed improvements
* Repair testthat tests

# heatwaveR 0.2.6.9001 (2018-05-24)

* Moved all vignettes relating to the upcoming MHW_detection paper to that repo
* This helps to unclutter this repo as it should be primarily kept for package content

# heatwaveR 0.2.6.9000 (2018-05-23)

* Added vignette that shows how tweaking arguments for detect changes the outputs
  between languages and how those outputs may differ
* Changed output of `detect_event` to better match Python version
* Corrections to testthat to match changes to `detect_event` output

# heatwaveR 0.2.5.9003 (2018-05-22)

* Added C++ function, `clim_calc_ccp()` for faster climatology calculations; speed
  of climatology calculation comes down from 50.6 ms in R to 3.4 ms in C++ on
  my MacBook Pro (15-inch, 2017) 2.9 GHz Intel Core i7 16 GB RAM computer

# heatwaveR 0.2.4.9003 (2018-05-21)

* Updated testthat for `lolli_plot()` and `event_line()`
* Updated testthat for `ts2clm()`
* Updated testthat for `detect_event()`

# heatwaveR 0.2.4.9002 (2018-05-17)

* Take advantage of C++ speed enhancement in `smooth_percentile()` by using
  RcppRoll
* Update testthat accordingly

# heatwaveR 0.2.3.9002 (2018-05-17)

* Basic R vs Python vignette finished

# heatwaveR 0.2.3.9001 (2018-05-16)

* Minor fix to testthat
* codecov up to 100%
* Fix to `geom_lolli()` n argument
* Fix to `lolli_plot()` y-axis range
* Minor fix to `make_whole()`
* Skeleton of R vs Python vignette added

# heatwaveR 0.2.3.9000 (2018-05-16)

* Major speed-up in the climatology creation function. `clim_spread()` now returns
  a matrix, not a data frame. This makes the loop in `clim_calc()` much faster.
  In testing with the sst_WA data, it leads to a 3.7 fold speed improvement
  (520 ms down to 140 ms).
* Speed-up of `make_whole()` (60 ms down to 40 ms)

# heatwaveR 0.2.2.9000 (2018-05-15)

* Removed all instances of `detect()` in favour of the new pipeline
* Updated `exceedance()` to utilise the internal functions
* Updated object names in `block_average()`

# heatwaveR 0.2.1.9001 (2018-05-15)

* Micro edits to documentation
* Testing for all exported and internal functions brought up to speed
* Ensuring that new `ts2clm()` and `detect_event()` pipeline returns the same
  results as the old `make_whole()` and `detect()` pipeline

# heatwaveR 0.2.1.9000 (2018-05-14)

* Phasing in identical names as in the python version
* `detect_event()` now passing checks
* Must still test for MCSs
* The old `detect()` function was unpacked and simplified. Internal code is now
  in new functions, most of which will not be seen by the user. They are `make_whole()`
  `proto_event()`, `clim_calc()`, `smooth_percentile()`, `clim_spread()`, and
  `ts2clm()`
* `ts2clm()` used instead of `detect_clim()`
* Climatologies can now be calculated independently of the detect functionality
* `exceedance()` function testthat checks updated to account for change in
  variable naming

# heatwaveR 0.2.0.9000 (2018-05-11)

* `detect()` has now been broken into `detect_clim()` and `detect_event()`
* These now also rely on internal functions
* The purpose of this is to create a family of functions that provide different options
* New vignette on making short climatologies.

# heatwaveR 0.1.0.9000 (2018-05-10)

* One may now provide alternative baselines and climatologies to `detect()`

# heatwaveR 0.0.7.9001 (2018-05-05)

* Testing for `category()`
* Testing for `block_average()`
* Testing for `detect()`
* Testing `exceedance()`
* Removed default `threshold` for `exceedance()`
* Tweaks to `exceedance()` error messages
* Testing for `event_line()`
* Testing for `lolli_plot()`
* Tweaks to `lolli_plot()` error messages

# heatwaveR 0.0.7.9000 (2018-05-04)

* New `category()` function returns the category results for events
* Still requires testing and improved event naming scheme

# heatwaveR 0.0.6.9000 (2018-05-03)

* Minor touch up to examples in `geoms.R`
* First draft of `heatwaveR` hex logo added to site
* Added `category` option to `event_line()`
* Simplifications and consistency checks to `detect()`
* Some writing on Baselines and climatology vignette

# heatwaveR 0.0.5.9001 (2018-05-02)

* Fix to `event_line()` not plotting MCSs correctly
* Fix error with smooth_percentile and smooth_percentile_width descriptions
  that were interchanged in `detect()`
* Simplify initial lines of leap year calculations (remove redundant code)
* change from `raster::quantile()` to `stats::quantile()`

# heatwaveR 0.0.5.9000 (2018-04-29)

* Add option to use a custom baseline to `detect()` as requested by
  Maxime Marin (), The University of Tasmania (IMAS) – CSIRO (O&A),
  and which is present in the python version of the package

# heatwaveR 0.0.4.9000 (2018-04-28)

* Remove restriction to require full years for start/end points of
  climatology calculations in `detect()`
* Documentation updated accordingly
* Vignette on OISST data processing added

# heatwaveR 0.0.3.9000 (2018-04-26)

* Removed rlang dependency
* Touch-up to `block_average()`
* Tested `make_whole()`
* Basic testing for other functions

# heatwaveR 0.0.2.9000 (2018-04-25)

* Established theme for changelog
* Synced ganalytics
* Fixed `event_line()` to acknowledge column names other than `t` and `temp`
* Fixed `lolli_plot()` to use underlying `geom_lolli()`
* Search bar now live
* Removed all but one use of plyr code

# heatwaveR 0.0.1.9000 (2018-04-24)

* Added a `NEWS.md` file to track changes to the package.
* Cloned __`RmarineHeatWaves`__ package to this repo
* First build of __`pkgdown`__ site live
