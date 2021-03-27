---
autogenerated: true
title: SNT › Analysis
layout: page
categories: SNT
description: test description
---

{% include sntnavbar%}


<div class="toclimit-3">

Sholl Analysis
==============

There are two [Sholl Analysis](https://imagej.net/Sholl_Analysis) commands available in SNT's *Analysis* menu. The {% include bc content='Analysis|Shuoll Analysis...'%} option provides a set of pre-defined focal points the user can choose from. Note for the morphology-based focal points (e.g., *Soma*, *Root node(s): Primary apical dendrite(s)*) , the relevant morphology tag(s) must be assigned to the set of paths considered by the analysis. To select a focal point manually, see the following section.

Sholl Analysis (by Focal Point)
-------------------------------

<img src="/media/Snt-Sholl-Coarse-Intructions.png" title="fig:Initiating Sholl Analysis: coarse method" width="200" alt="Initiating Sholl Analysis: coarse method" /> It is also possible to initiate [Sholl Analysis](https://imagej.net/Sholl_Analysis) on a tracing in the canvas by manually selecting a focal point. You can do it coarsely by right-clicking near a node and choosing *Sholl Analysis at Nearest Node* from the contextual menu (Shortcut: {% include key content='Alt' %} + {% include key content='Shift' %} + {% include key content='A' %}.

Alternatively, for precise positioning of the center of analysis:

1.  Mouse over the path of interest. Press {% include key content='G' %} to activate it.
2.  Press {% include key content='Alt' %}+{% include key content='Shift' %} to select a node along the path.
3.  Press {% include key content='Alt' %}+{% include key content='Shift' %}+{% include key content='A' %} to start analysis.

<div align="center">

-   <img src="/media/Snt-Sholl-Precise-Step-1.png" title="fig:1) Select path" width="200" alt="1) Select path" />
-   <img src="/media/Snt-Sholl-Precise-Step-2.png" title="fig:2) Snap cursor to node" width="200" alt="2) Snap cursor to node" />
-   <img src="/media/Snt-Sholl-Precise-Step-3.png" title="fig:3) Sholl dialog" width="146" alt="3) Sholl dialog" />

</div>

{% include clear%}
 The Sholl dialog created by this approach differs slightly from the dialog created by running the {% include bc content='Analyze|Sholl|Sholl Analysis (From Tracings)...'%} plugin in the main Fiji menu. First, the center of analysis is automatically taken from the nearest (or exact) node where the user clicks. In addition to morphology and custom tag filters, the *Path filtering* drop-down menu provides an additional option to restrict the analysis to the subset of paths selected in the Path Manager. Another advantage is that the display canvas allows the radius step size to be previewed visually. To do this, toggle on the *Preview* checkbox under the *Sampling* section and experiment with different step sizes.

<div align="center">

-   <img src="/media/Snt-Sholl-preview-step-size-1.png" title="fig:Step Size = 0" width="200" alt="Step Size = 0" />
-   <img src="/media/Snt-Sholl-preview-step-size-2.png" title="fig:Step Size = 5" width="200" alt="Step Size = 5" />

</div>

In addition to the Sholl Profile plot and table, the output of the analysis can be visualized as a color mapping of the reconstruction and as a [Sholl Image](https://imagej.net/Simple_Neurite_Tracer:_Sholl_analysis#Sholl_Image). To color code the tracing, choose *Color coded paths* from the *Annotations* drop-down menu and select a Lut from the *Annotations Lut* drop-down menu before pressing *Run Analysis*. To output the Sholl Image, choose *3D viewer labels image* from the *Annotations* drop-down menu and select the desired Lut before running the analysis.

<div align="center">

-   <img src="/media/Snt-Sholl-Profile-Plot-New.png" title="fig:Sholl Profile Plot" width="305" alt="Sholl Profile Plot" />
-   <img src="/media/Snt-Sholl-Profile-Table-New.png" title="fig:Sholl Profile Table" width="230" alt="Sholl Profile Table" />
-   <img src="/media/Snt-Sholl-Color-Map.png" title="fig:Color Coded Tracing - Ice Lut" width="200" alt="Color Coded Tracing - Ice Lut" />
-   <img src="/media/Snt-Sholl-Color-Map-Mask.png" title="fig:Sholl Image - Ice Lut" width="200" alt="Sholl Image - Ice Lut" />

</div>

Strahler Analysis
=================

To conduct [Strahler Analysis](https://imagej.net/Strahler_Analysis) on the current contents of the Path Manager, choose the {% include bc content='Utilities|Strahler Analysis'%} command in the main SNT dialog. This command will output the results of the analysis as a table and plot. These figures contain morphometric statistics on the group of paths associated with each Horton-Strahler Number. Note that this feature analyzes traced reconstructions. To run Strahler analysis on images, use the {% include bc content='Analyze|Skeleton|Strahler Analysis...'%} plugin in the main Fiji dialog.

<div align="left">

-   <img src="/media/SNT-Strahler-Analysis-Table.png" title="fig:Strahler Analysis table" width="200" alt="Strahler Analysis table" />
-   <img src="/media/SNT-Strahler-Analysis-Plot.png" title="fig:Strahler Analysis plot" width="200" alt="Strahler Analysis plot" />

</div>

Path Order Analysis
===================

Found at {% include bc content='Analysis|Path Order Analysis'%} in the main SNT dialog, this option analyzes the Paths in the Path Manager based on [Branch Order](https://www.mbfbioscience.com/help/nx11/Content/Branch%20order/Branch_Order.htm). Produces a table of results and a plot similar to the *Strahler Analysis* option, with morphometric statistics on the group of paths associated with each Branch Order.

<div align="left">

-   <img src="/media/SNT-Path-Order-Analysis-Table.png" title="fig:Path Order Analysis table" width="200" alt="Path Order Analysis table" />
-   <img src="/media/SNT-Path-Order-Analysis-Plot.png" title="fig:Path Order Analysis plot" width="200" alt="Path Order Analysis plot" />

</div>

Measurements
============

<img src="/media/Snt-Measurements-List.png" title="fig:Measure... dialog" width="120" alt="Measure... dialog" /> SNT provides several ways to measure reconstructions. A comprehensive selection of measurements can be found by going to {% include bc content='Analysis|Measure...'%}. in the main SNT dialog. Note that for this option, if multiple rooted tree structures exist in the Path Manger, you will be prompted to choose one for analysis.

To quickly measure all existing paths with a common set of statistics, choose {% include bc content='Analysis|Quick Measurements'%}. In both cases the results of the measurements are displayed in a table.

To get measurements only on a select group of Paths, first select or filter for the Paths you want to measure in the Path Manager, then choose either command from the {% include bc content='Analyze'%} menu in the Path Manager.

Batch measurements of reconstructions can be accomplished via scripting. See *Measure\_Multiple\_Files.py* in the SNT [Script Templates](https://imagej.net/SNT:_Scripting#Script_Templates) for a basic example. \[\[Image:Snt-Measure-Results-Table.png\|none\|thumb\|1000px\|*Measure...*

`results]]`

{% include clear%}


Dendrogram Viewer
=================

<img src="/media/Snt-Dendrogram-Shortcuts.png" title="fig:Dendrogram Viewer shortcuts" width="140" alt="Dendrogram Viewer shortcuts" /> Found at {% include bc content='Utilities|Create Dendrogram'%}, this option generates a [Dendrogram](https://en.wikipedia.org/wiki/Dendrogram) from one connected component (i.e., a single rooted tree structure) in the Path Manager, providing a high-level overview of neurite branching topology. Note that if multiple rooted trees exist in the Path Manager, you will be prompted to choose one of them.

The viewer provides controls for orientation, zoom level, panning, vertex editing and traversal as well as options to display vertex labels and edge weights (which by default are the euclidean distances between adjacent vertices). To see the available key shortcuts, right click on the viewer and choose *Available Shortcuts...*. The plot may be exported in several file formats, including HTML, PNG and SVG.

Fine-grained programmatic control over SNT's Graph objects is achieved using the [JGraphT API](https://jgrapht.org/javadoc/) in a script. Also relevant is the [sc.fiji.snt.analysis.graph](http://fiji.github.io/SNT/sc/fiji/snt/analysis/graph/package-frame.html) package which provides high-level tools for Graph creation and conversion. See *Graph\_Analysis.py* in the SNT [Script Templates](https://imagej.net/SNT:_Scripting#Script_Templates) for a basic example. <img src="/media/Snt-Dendrogram-Viewer.png" title="fig:Dendrogram Viewer" width="300" alt="Dendrogram Viewer" />

Comparing Reconstructions
=========================

The {% include bc content='Utilities|Compare Reconstructions...'%} command will bring up a prompt which gives the user the option to compare two single reconstruction files against multiple metrics, or multiple groups of reconstruction files against a single metric.

<figure><img src="/media/Snt-Compare-Reconstructions-Single-Or-Group-Choice.png" width="200" /></figure>

If you select, *Compare two files* and press *OK*, a file chooser dialog will appear allowing the user to select two SWC files and their respective colors for display in Reconstruction Viewer.

<figure><img src="/media/Snt-Compare-Reconstructions-Single-File-Chooser.png" width="200" /></figure>

<figure><img src="/media/Snt-Compare-Reconstructions-Single-3DViewer-Result.png" width="200" /></figure>

Use the *Browse* button to select the two files and press 'OK' to run the analysis. The results will include a table containing results of the *Quick Measurements* function for both reconstructions, as well as an instance of the 3D Reconstruction Viewer displaying both reconstructions. <img src="/media/Snt-Compare-Reconstructions-Single-Measurements-Table.png" title="fig:" width="900" /> {% include clear%}
 To instead compare multiple groups of reconstruction files against a single metric, choose *Compare groups of cells (two or more)* in the initial prompt.

<figure><img src="/media/Snt-Compare-Reconstructions-Group-File-Chooser.png" width="200" /></figure>

The file selection prompt for this option allows selection of up to four directories containing SWC files. The metric to compare against is chosen from the *Metric* drop-down menu. Optionally, the user may restrict the analysis to specific neurite compartments. After making your selections, press *OK* to run the analysis. The result include multi-panel figure(s) rendering up to ten reconstructions from each group, a window with the metric statistics on each group, a box-plot and a histogram. These figures can all be exported as PNG or SVG.

<div align="center">

-   <img src="/media/Snt-Compare-Reconstruction-Group-Render1.png" title="fig:" width="350" />
-   <img src="/media/Snt-Compare-Reconstruction-Group-Render2.png" title="fig:" width="350" />

</div>
<div align="center">

-   <img src="/media/Snt-Compare-Reconstruction-Group-Statistics-Window.png" title="fig:Snt-Compare-Reconstruction-Group-Statistics-Window.png" width="300" alt="Snt-Compare-Reconstruction-Group-Statistics-Window.png" />
-   <img src="/media/Snt-Compare-Reconstruction-Group-Box-Plot.png" title="fig:" width="200" />
-   <img src="/media/Snt-Compare-Reconstruction-Group-Histogram.png" title="fig:" width="300" />

</div>

Custom Analyses
===============

It is possible to script your own analysis routines. See [SNT:\_Scripting](https://imagej.net/SNT:_Scripting) for the link to SNT's API as well as script templates demonstrating a range of analysis possibilities.

{% include sntnavbar%}


 