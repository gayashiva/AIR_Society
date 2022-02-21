# Workflow steps
1. Use representative winter and summer EB to create AIR Index (AI) for a given location.
2. Intersect AI with demand index (DI) and supply index (SI) from [Immerzeel et al.
   (2019)](https://doi.org/10.1038/s41586-019-1822-y) to create AIR Suitability Index (ASI).

# Key questions
1. **How to define an AIR index (AI) ?** 
    * We have to derive a representative winter (WEB) and summer energy balance (SEB) using historical weather
      data. The winter EB is indicative of the freezing rate or maximum ice volume expected and the summer EB is
      a proxy for the survival duration or the melting rate expected.  For example, AI = -(WEB + SEB). High AI
      either means large AIRs (High WEB) or long lasting AIRs (Low SEB). We could also compare this index using
      Ladakh's and Swiss WEB and SEB. We can define favourable locations as AI_{Swiss} <= AI_{location}.
      Additionally, locations that also satisfy AI_{location} <=AI_{Swiss} can be categorised as Perrenial Ice
      Reservoirs (PIRs).
    * Another possibility is to define AI from temperature and altitude. In the figure below, the distribution
      of expected freezing rate during winter nights is shown. Note that this estimation assumes a constant wind
      speed (2 m/s), humidity (50%) and cloudiness(0.5). The Swiss (Guttannen) and Indian (Gangles) location are
      highlighted based on their mean winter temperature and altitude.

![AIR Index](figs/alt_temp.png)

2. **How to use SIs and DIs in combination with AI to quantify the AIR Suitability Index (ASI)?**
    * Regions with a high DI and with low SI would be excellent candidates. However, we should find a
      threshold/criteria for the water supply. SIs include four different factors for water availability:
      surface water (L), glacier (G), snow (G) and precipitation (P). I think we should target regions with
      high/medium L, G and S and low P. If we cross these with areas with a high DI, we will target areas where
      the use of AIRs would be very suitable. Then, by crossing this with the results of the previous analysis
      of climate suitability we should be able to identify the suitable areas for AIRs.

3. **How to constrain ERA5 grid points for simulations?**
    * Use Randolph Glacier Inventory (RGI) to capture all suitable areas near glacial water source.
    * Use ? to capture all suitable areas near surface water.
    * Use population criterion 

## Next Steps
1. Calculate AI for Ladakh using ERA5 data. Produce freezing rate, evaporation-precipitation plot. (Surya)  

## Data for analysis
1. ERA5: 
    (a) Mean land temperature in at least 3 months of the year is subzero. 
    (b) Altitude (or air humidity?) of the region atleast ?
2. The easiest option would be to use SIs from Immerzeel et al. (2019). An alternative, to go into more detail
   would be to use inventories of glacial lakes. These products are only available per region. Andes: Central
   and Patagonian Andes - [Wilsont et al. (2018)](https://doi.org/10.1016/j.gloplacha.2018.01.004), Peruvian
   Andes - [Wood et al. (2021)](https://doi.org/10.1016/j.gloplacha.2021.103574). High Mountain Asia: [Wang et
   al. (2020)](https://doi.org/10.5194/essd-2019-212). 
3. Population-wise, the easiest option would be to use DIs from Immerzeel et al. (2019). If we want to make our
   own calculations and to produce results at a higher spatia resolution we could use
   [GPWv4](https://sedac.ciesin.columbia.edu/data/collection/gpw-v4) for global population.  

## References
1. Wilhelm Furian, Fabien Maussion and Christoph Schneider, Projected 21st century glacial lake evolution in High Mountain Asia, https://www.frontiersin.org/articles/10.3389/feart.2022.821798/abstract
2. Immerzeel, W.W., Lutz, A.F., Andrade, M. et al. Importance and vulnerability of the world’s water towers. Nature 577, 364–369 (2020). https://doi-org.proxy.library.uu.nl/10.1038/s41586-019-1822-y
3. Wang, X., Guo, X., Yang, C., Liu, Q., Wei, J., Zhang, Y., Liu, S., Zhang, Y., Jiang, Z., and Tang, Z.: Glacial lake inventory of high-mountain Asia in 1990 and 2018 derived from Landsat images, Earth Syst. Sci. Data, 12, 2169–2182, https://doi.org/10.5194/essd-12-2169-2020, 2020. 
