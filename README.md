# Caitlyn Linehan
 
I teach GEG-8 at Riverside City College and study walkability and access to green space in cities. This page is the worked example for the midterm portfolio lab. Everything here was built with the same tools and written to the same instructions you have, so you can see what a finished entry looks like before you write your own.
 
---
 
## How Far the Ground Dropped During the 2018 Kilauea Eruption
 
![Short description of the map for screen readers](images/displacement.avif)
 
 
**Question:** How much did the surface of Hawaii Island move vertically in the twelve days spanning the start of the 2018 Kilauea eruption, and where was that movement concentrated?
 
**Data:** Sentinel-1 synthetic aperture radar scenes from April 23 and May 5, 2018, obtained through the Alaska Satellite Facility DAAC. The scenes contain modified Copernicus Sentinel data processed by ESA. GPS station locations come from SONEL and the Hawaiian Volcano Observatory. Basemap from Esri, USGS, and NOAA.
 
**Method:** I built a differential interferogram from the two radar scenes in the ESA Sentinel Application Platform, unwrapped the phase, and converted the result to vertical displacement in meters. I mapped the displacement surface over shaded relief and left the rest of the island as bare hillshade, so the shape of the island stays readable and the measured signal is visibly confined to where it exists. GPS station locations are drawn on top as reference points. The inset zooms to the southeastern flank, where the largest values sit.
 
**A design choice I made and why:** All the values run from zero downward, so I used a single sequential ramp anchored at zero rather than a diverging scheme. A diverging ramp would have implied a meaningful midpoint and invited the reader to see uplift where there is none. Every hue on this map means subsidence, and only the amount changes.
 
**A limitation of this map:** Radar interferometry measures displacement along the satellite line of sight, so horizontal motion from rift opening is folded into what is presented here as vertical change. The result is also relative to a reference area assumed to be stable, and it covers one twelve day interval rather than the eruption as a whole. Areas where the surface changed too much between passes lose coherence and carry no reliable value at all.
 
---
 
## Ozone Exposure Across New York Counties, and What the Interpolation Method Changes
 
![Short description of the map](images/Linehan_Lab_C_Final.avif)
 
**Question:** Where was ozone exposure highest across New York State counties in 2010, how much does the answer depend on the interpolation method used to get there, and does exposure track the racial composition of a county?
 
**Data:** Daily maximum ozone concentrations in parts per million from Environmental Protection Agency monitoring stations, 2010. County population by race from the United States Census Bureau, 2010.
 
**Method:** Ozone readings exist only at monitoring stations, so I interpolated a continuous surface from the point data twice, once with Thiessen polygons and once with inverse distance weighting. I assigned each county an estimated concentration from each surface, then calculated Pearson correlations between those estimates and the percentage of the county identifying as non-Hispanic White, non-Hispanic Black, and Hispanic.
 
**A design choice I made and why:** I showed both interpolation surfaces side by side instead of choosing the better one. Presenting a single surface would have hidden the fact that the method is a choice, and putting them next to each other lets the reader see the answer for themselves: the two sets of county estimates correlate at 0.966, so the substantive pattern survives the choice of method. That is a stronger claim than either map makes alone.
 
**A limitation of this map:** Correlations calculated on counties describe counties, not people. A county where exposure is high and the non-Hispanic White share is low does not tell you what any individual in that county breathes, and treating it as if it does is the ecological fallacy. Monitoring stations are also sited deliberately rather than randomly, and both interpolation methods invent values across the large parts of the state where no station exists.
 
---
 
## Data sources
 
- Alaska Satellite Facility DAAC, 2019. Sentinel-1 SLC scenes, April 23 and May 5, 2018. Contains modified Copernicus Sentinel data 2018, processed by ESA. https://asf.alaska.edu/
- SONEL and the USGS Hawaiian Volcano Observatory. GPS station locations, accessed November 2019.
- United States Environmental Protection Agency, 2010. Ozone monitoring station daily summary data. https://www.epa.gov/outdoor-air-quality-data
- United States Bureau of the Census, 2010. County population by race.
 
## Where this is going
 
Two more maps go on this page before the end of the term. I want the finished page to show two things at once: that I can run a technical workflow from raw data to a finished product, and that I can say out loud what each map assumes and what it leaves out. The second one is harder, and it is the one that gets people hired.
