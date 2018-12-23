Linked Views for Tracking Daily Diabetes Measurements 
(found at https://RussellMDavis.github.io/Diabetes-Uncertainty-Vis-Idea/)
===
Summary:

Type 1 Diabetes is often managed using a Continuous Glucose Monitor, which has proven to be more effective than most other
available tools.  However, CGM software lacks effective visualization and does not properly capture the uncertainty inherent
in biological readings.  This set of visualizations is intended to address both concerns.

USERS NOTE: THE DIAGRAMS ARE LINED UP BEST AND MOST EASILY VIEWED WHEN THE BROWSER IS SET AT 80% MAGNIFICATION.

Managing Type 1 Diabetes is a life-long task that requires significant time investment for those with the condition.  Effective
management usually involves retrospective analysis of trends in their blood sugar levels collected from medical devices.
Because daily life is often routine, retrospective analysis can reveal relevant trends (e.g. Is my blood sugar often
especially high in the morning when I wake up, or does it regularly drop low in the evenings?).


Understanding the Scatter Plot
==
During daily use, the devices currently available primarily show a line chart of blood sugar for the most recent 6-24 hours.  This is
mirrored in the scatter chart displayed in the visualization, which shows a theoretical individual's experience for a given 24-hour
period from 12:00 AM to 11:59 PM.  The graph includes threshold lines at 50 and 200 milligrams of glucose per deciliter of blood
which is the standard American unit of measurement.  These threshold lines represent approximate levels for hypoglycemia and
hyperglycemia, respectively, which are conditions of unhealthy blood sugar levels.
In order to properly mirror the notion of retrospection, blood sugar was modeled for this theoretical individuals for 28 different days,
each choosable from the selection menu.

Scatter Plot Interactivity
=

The scatter plot supports brushing, which allows the user to select a subset of the points.  This subset will be used to as an
alternate set of data for creating the Blood Sugar Histogram and Time of Day Bar Chart (discussed below).
The default visualization upon loading the page shows the scatter plot with all points brushed.

Understanding the Histogram
==
HeThe histogram shows the distribution of the blood glucose levels shown as points, allowing users to see the overall quality of their
blood sugar levels.  For example, the default distribution shown for Day 1 shows that this individual had relatively high blood
sugar levels, with a bimodal distribution centered around 170 and 270.  This information is useful for assessing overall blood
sugar levels.  The default visualization upon loading the page shows the histogram for all times during that day.

Blood Sugar Histogram Interactivity
=

By mousing over a column in the histogram, the user can see the times of day that those blood sugar values came from in the Time of
Day Bar Chart (discussed below).  The mouseover will also highlight the instances of those blood sugar values in the scatter plot.

Understanding the Time of Day Bar Chart
==

The bar chart shows the time of day that various blood sugar levels occurred.  The default visualization contains all points.  However,
upon brushing in the main chart or mousing over in the histogram, a subset of those values will be displayed.  This is the
primary intended purpose, and will give the user a clear idea of the time of day that blood sugar levels occurred.

Time of Day Bar Chart Interactivity
=

Hovering over a bar in the bar chart will turn the corresponding instances in the scatter plot gold, to make it clear what the
corresponding instances are for that time of day.  Because the bar chart is ultimately a summary of the histogram, action on the
bar chart is not reflected in the histogram.

Understanding the Error Slider
==
A personal project of mine is to highlight the uncertainty of measurements made by diabetes management devices.  The slider
allows the user to manually set a percent error in the measurement to see the effect of this concept.  The default is set to 0%, which
is what is shown by the medical device.  Diabetes management devices are generally marketed as having an average error of 10%, 
but the error can go as high as 20% depending on use context.  This tool was designed to allow the user to understand
the implications of this idea.

Error Slider Interactivity
=

Changing the slider will generate error bars on the main graph.  It will also adjust the histogram; rather than determining frequency by
aggregating the stated value of each point on the scatter plot into bins, it will randomly select a value from the range of
possible values for each point based on the error setting.  By changing the setting and seeing how the distribution changes,
users can get an idea for what their distribution might be when accounting for uncertainty in measurements.


References
===

Help with axes and labels came from https://bl.ocks.org/d3noob/23e42c8f67210ac6c678db2cd07a747e

Help with creating the bar chart came from https://bost.ocks.org/mike/bar/3/

Some ideas for designing the brush came from http://bl.ocks.org/feyderm/6bdbc74236c27a843db633981ad22c1b

Help with the slider (https://bl.ocks.org/mbostock/6452972) and various d3 formatting issues came from Mike Bostock
