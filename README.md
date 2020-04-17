# physics_project
## Analyzing data from MAGIC Gamma Telescope

Source:
R. K. Bock
Major Atmospheric Gamma Imaging Cherenkov Telescope project (MAGIC)
http://wwwmagic.mppmu.mpg.de
rkb@mail.cern.ch

Columns:
1.  fLength:  continuous  -  major axis of ellipse [mm]
2.  fWidth:   continuous  - minor axis of ellipse [mm] 
3.  fSize:    continuous  - 10-log of sum of content of all pixels [in #phot]
4.  fConc:    continuous  - ratio of sum of two highest pixels over fSize  [ratio]
5.  fConc1:   continuous  - ratio of highest pixel over fSize  [ratio]
6.  fAsym:    continuous  - distance from highest pixel to center, projected onto major axis [mm]
7.  fM3Long:  continuous  - 3rd root of third moment along major axis  [mm] 
8.  fM3Trans: continuous  - 3rd root of third moment along minor axis  [mm]
9.  fAlpha:   continuous  - angle of major axis with vector to origin [deg]
10.  fDist:    continuous  - distance from origin to center of ellipse [mm]
11.  class:    g,h  - gamma (signal), hadron (background)

Goal: classification taking class (gamma/hadron) as a dependent variable. 
Result: After gridsearch XGBoost model achieved 91.27% validation accuracy.

## Classes

![Classes](img/classes.png)

## Distributions of the variables

![10_log_sum_pixels](img/10_log_sum_pixels.png)

![angle_minor](img/angle_minor.png)

![dist_origin_center](img/dist_origin_center.png)

![dist_pixls](img/dist_pixls.png)

![maxor_axis_distplot](img/maxor_axis_distplot.png)

![minor_axis_distplot](img/minor_axis_distplot.png)

![pixels_size](img/pixels_size.png)

![ratio_pixels](img/ratio_pixels.png)

![root3_moment](img/root3_moment.png)

![root3_moment_minor](img/root3_moment_minor.png)

## Modeling results

XGBoost model without gridsearch

![xgboost_report](img/xgboost_report.png)

XGBoost model after gridsearch

![gridsearch_params](img/gridsearch_params.png)
