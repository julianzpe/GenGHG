# GenGHG
Generative Design Tool to Reduce Embodied GHG Emissions in High-Rise Residential Buildings.
This work was developed as part of a M.A.Sc. thesis in Civil Engineering at the University of Toronto by Julian Zaraza. The thesis was supervised by Prof. Daniel Posen and Prof. Brenda McCabe. The author acknowledges the support of EllisDon, BASF Canada and WSP, as well as matching funds from the Natural Sciences Research Council of Canada (CRDPJ 508960) and the Ontario Centres of Excellence (TargetGHG 27943).

![GenGHG Banner](https://julianzaraza.page.link/github-banner)

# How to use GenGHG?
The main Dynamo graph is [20200817_GenGHG_457_core.dyn](https://github.com/julianzpe/GenGHG/blob/master/20200817_GenGHG_457_core.dyn). Make sure you download and install all [dependencies](https://github.com/julianzpe/GenGHG#dependencies), [third-party packages](https://github.com/julianzpe/GenGHG#packages-list), and [custom nodes](https://github.com/julianzpe/GenGHG#custom-nodes). Also, make sure your computer recognizes the path of both the 1. Site Conditions and 2. CSV Imports folders. To achieve that, create those two folders within the folder where the main Dynamo file lives (i.e. GenGHG_457_core.dyn). For methodology questions please refer to the project's public thesis or publications (search in  [Automation in Construction](https://www.sciencedirect.com/journal/automation-in-construction) and look for Julian Zaraza as main author).

* The following is a screen capture of the entire GenGHG Dynamo graph broken down by functionality. Please note that the Geometry System step is condensed into a single custom node which is available to download in the [custom nodes section](https://github.com/julianzpe/GenGHG#custom-nodes) of this repository.

![GenGHG Full Dynamo Graph](https://julianzaraza.page.link/genghg-summary)

# Required files
## Site Conditions Files
Download from [1. Site Conditions](https://github.com/julianzpe/GenGHG/tree/master/1.%20Site%20Conditions)

- 20200228_Site-Conditions_Landmarks.obj
- 20200228_Site-Conditions_Parks_1.obj
- 20200228_Site-Conditions_Topo_1.obj
- 20200228_Site-Conditions_Water_1.obj

The previous four .OBJ files contain the information that describes the surrounding conditions of the site. These were used for the case study described in the original study. Replace them with your study's information following the same order and categorization.

- 20200312_Massings_SemiDetailed.obj: Contains a simplified mesh for each of the site's surrounding buildings. Used for intersection calculations which is part of the views analysis. 

- 20200405_Site-Conditions_Massings_5.obj: Contains detailed mesh of surrounding buildings for visualization purposes only

<p align="center">
<img src="https://julianzaraza.page.link/genghg-thumbnail" width=50% height=50%>
</p>

## CSV Imports
Download from [2. CSV Imports](https://github.com/julianzpe/GenGHG/tree/master/2.%20CSV%20Imports)
- x.csv, y.csv, z.csv: X,Y,Z coordinates for target points for views analysis

- x_mass.csv, y_mass.csv, z_mass.csv: X,Y,Z coordintes for building site footprint 

- lca_factors.csv: Structural and envelope LCA factors for embodied GHG emissions calculation

- material_estimates.csv: Normalized estimates for concrete (in cubic meters/volume of building space in cubic meters) and rebar (in metric tons or Mg per Mg of concrete).

<p align="center">
  <img src="https://julianzaraza.page.link/genghg-sitecond-gif">
</p>

# Dependencies
All the following items are required for running GenGHG. Newer versions might work but full functionality is not ensured. There are some known issues with using newer versions of Refinery, such as Generative Design for Revit. These are easily corrected by changing all Refinery 0.62.2 nodes by "Generative Design for Revit" nodes, which are named very simlarly.

### Dynamo 2.6.0 
Download from [Dynamo's site](https://www.dynamobim.org)

### Packages
Copy all packages into your local Dynamo installation or download each of them directly from package manager (make sure version does not change). 

* Typical local directory C:\<user>\AppData\Roaming\Dynamo\Dynamo Core\2.<version>\packages. 
* Download from [0. Packages and Installers](https://github.com/julianzpe/GenGHG/tree/master/0.%20Packages%20and%20Installers)
  
####    Packages list
- LunchBox for Dynamo (v2018.7.6)
- Dynamo Text (v2.0.1)
- MeshToolkit (v2.0.1)
- Refinery (v0.62.2)
- spring nodes (v203.1.0)
- Ampersand (v2019.12.31)
- Clockwork for Dynamo 2.x (v2.3.0)
- Topologic (v1.0.0)

### Design Generation Module (Custom Node):
- Download from [GenGHG_GeometrySYS_2.dyf](https://github.com/julianzpe/GenGHG/blob/master/GenGHG_GeometrySYS_2.dyf)

This study proposes a novel geometry system for the generation of realistic, modern-looking, tall residential building shapes. The steps of the system are described in the paper published in the journal Autom. in Construction. The steps are a series of geometric operations that through translation, intersection, subdivision, and extrusion, are able to generate a building shape in one iteration. The steps are the result of several experimental tests for achieving a desired level of aesthetics and geometric variability within the shapes produced, and are based on the conceptual design assumptions. These assumptions are critical to frame the structure of the geometry system. These include architectural and geometric considerations that dictate the sections that are fixed and the ones that vary. For instance, it is provided that the tower shape may vary in geometry as long as it does so within the site boundary. In contrast, the podium and underground section are assumed to preserve the shape of the site, as this is common practice in downtown Toronto high-rise buildings since developers are bounded to maximize lot use. 

<p align="center">
<img src="https://julianzaraza.page.link/genghg-design-generation" width=50% height=50%>
</p>

