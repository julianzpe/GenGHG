# GenGHG
Generative Design Tool to Reduce Embodied GHG Emissions in High-Rise Residential Buildings.
This work has been developed as part of a M.A.Sc. thesis at the University of Toronto.


![GenGHG Banner](https://www.dropbox.com/s/5lsjhh7ih4tbfdg/2020.12.28%20Github%20Banner%202.png?raw=1)

# How to use GenGHG?
Make sure you download and install all dependencies and third-party packages. Also, make sure your computer recognizes the path of the following files for initial testing:
- Site Conditions 
- CSV Imports:
-- x.csv, y.csv, z.csv: X,Y,Z coordinates for target points for views analysis
-- x_mass.csv, y_mass.csv, z_mass.csv: X,Y,Z coordintes for building site footprint 
-- lca_factors.csv: Structural and envelope LCA factors for embodied GHG emissions calculation
-- material_estimates.csv: Normalized estimates for ammounts of concrete (in cubic meters/volume of building space in cubic meters) and rebar (in metric tons or Mg per Mg of concrete). Normalized per cubic meter of concrete of concrete (Mgcon), and cubic meters of building volume (conm3).

<p align="center">
  <img src="https://im3.ezgif.com/tmp/ezgif-3-a2ebc8af039f.gif">
</p>

# Dependencies
## Dynamo 2.6.0 (dynamobim.org)
### Packages: 
- LunchBox for Dynamo (v2018.7.6)
- Dynamo Text (v2.0.1)
- MeshToolkit (v2.0.1)
- Refinery (v0.62.2)
- spring nodes (v203.1.0)
- Ampersand (v2019.12.31)
- Clockwork for Dynamo 2.x (v2.3.0)
- Topologic (v1.0.0)
### Custom Nodes:
- GenGHG_GeometrySYS_2.dyf

<p align="center">
<img src="https://www.dropbox.com/s/535161oyug4u0zp/GenGHG_thumbnail.png?raw=1" width=50% height=50%>
</p>


