# WindEnergyYYC-Shafrick
This readme file was generated on [2024-11-25] by [NINA SHAFRICK]


GENERAL INFORMATION

Title of Project Package: GEOG587_-_Wind_Energy_VAWT_-_Shafrick

Student Researcher
Name: Nina Shafrick
Institution: University of Calgary
Address: 2500 University Dr NW, Calgary, AB T2N 1N4
Email: nurina.shafrick@ucalgary.ca | nurinashafrick@gmail.com

Instructor
Name: Victoria Fast
ORCID: 0000-0002-7093-3864
Institution: University of Calgary
Address: 2500 University Dr NW, Calgary, AB T2N 1N4
Email: victoria.fast@ucalgary.ca

Teaching Assistant
Name: Regan Martin
Institution: University of Calgary
Address: 2500 University Dr NW, Calgary, AB T2N 1N4
Email: regan.martin@ucalgary.ca

Date of data collection: 2024-09-16 to 2024-11-20

Geographic location of data collection: 51°02′51.94″ North, longitude 114°04′08.35″ West. Calgary, AB, Canada.



PROJECT PURPOSE

Assessing Wind Power Density and Energy Use for Renewable Energy Development in Calgary: The Future of Renewable (Wind) Energy in Calgary.
This project aims to identify key factors influencing renewable energy opportunities in Calgary's urban landscape to support the city's transition to net-zero carbon emissions by 2050.
The focus is on assessing the potential of vertical-axis wind turbines (VAWTs) in urban areas, given their efficiency in low wind speeds and turbulent conditions.
By analyzing variables like wind power density, energy use intensity, avoided emissions, and proximity to infrastructure, the project highlights optimal locations and strategies for integrating VAWTs.
The findings will help reduce reliance on natural gas, cut greenhouse gas emissions, and advance Calgary's sustainability goals.



DATA SOURCES

File List:

1. Folder name: 3DBuildings__COC
   Dataset: 3D Buildings - Citywide
   Description: Basemap of Calgary buildings
   Format: SHP
   Source: Calgary Open Data Portal
   Link: https://data.calgary.ca/Base-Maps/3D-Buildings-Citywide/cchr-krqg/about_data
   
2. Folder name: City Boundary__COC
   Dataset: City Boundary
   Description: Basemap of Calgary boundary
   Format: SHP
   Source: Calgary Open Data Portal
   Link: https://data.calgary.ca/Base-Maps/City-Boundary/erra-cqp9/about_data

3. Folder name: CommunityDistrictBoundaries__COC
   Dataset: Community District Boundaries
   Description: Basemap of community district boundaries of Calgary
   Format: SHP
   Source: Calgary Open Data Portal
   Link: https://data.calgary.ca/Base-Maps/Community-District-Boundaries/surr-xmvs/about_data

4. Folder name: ContoursLineAB_CAN_DMTI_2023
   Dataset: Contour Lines of Alberta (2023)
   Description: Contour lines of Alberta by DMTI Spatial
   Format: SHP
   Source: University of Calgary Spatial Data Services (SANDS)
   Link: https://sands.ucalgary.ca/datacatalogueget.php?file=Restricted/Elevation/ContoursLineAB_CAN_DMTI_2023.zip

5. File name: Building_Energy__COC
   Dataset: Building Energy Benchmarking – City of Calgary
   Description: Building energy and greenhouse gas emission performance information for a subset of properties owned and operated by the City of Calgary
   Format: CSV
   Source: Calgary Open Data Portal
   Link: https://data.calgary.ca/Environment/Building-Energy-Benchmarking-City-ofCalgary/8twd-upbv/about_data
   
6. File name: Streetlight_Poles__COC
   Dataset: Streetlight Poles
   Description: Location of streetlight poles in Calgary
   Format: CSV
   Source: Calgary Open Data Portal
   Link: https://data.calgary.ca/Health-and-Safety/Streetlight-Poles/vt3t-jpfj/about_data

7. File name: wind_powerdensity_10m
   Dataset: Mean Wind Power Density at 10m elevation - Calgary clip
   Description: Wind power density (W/m2) of Calgary at 10m elevation
   Format: TIFF
   Source: Global Wind Atlas
   Link: https://globalwindatlas.info/en/



METHODOLOGICAL INFORMATION

Description of methods used for collection/generation of data:
Data Sources:
  City of Calgary Open Data Portal: Obtained datasets for 3D building information (used to calculate building heights), streetlight poles, and building energy data (including Source EUI and avoided emissions).
  Global Wind Atlas: Downloaded Wind Power Density (WPD) data at 10m elevation as a raster file.

References:
  Energy Star (2024) for selecting Source EUI as the preferred metric for total energy use.
  The City of Calgary (2024) for benchmarks in building height classifications.
  Havre (2022) for height classifications of low-rise buildings and general skyscraper benchmarks.

Methods for processing the data:
1. Preprocessing and Geospatial Adjustments:
    Geocoded building energy datasets to building addresses in ArcGIS Pro.
    Clipped contour lines and wind power density raster to Calgary's boundary for refined analysis.
    Calculated building heights using field calculations:
    Building Height = z-axis rooftop elevation − max z-axis ground elevation
2. Raster Conversion:
    Converted 3D building data into a raster layer for height classifications (8m, 23m, 100m, >100m).
    Applied the Point to Raster tool for streetlight poles, Source EUI, and avoided emissions.
    Generated proximity rasters for streetlights using the Multiple Ring Buffer tool (50m, 150m, 300m distances).
3. Data Normalization:
    Reclassified datasets to a uniform scale of 50, 75, or 100 based on suitability for vertical-axis wind turbines (VAWTs).
    Parameters for normalization:
      Higher scores for lower wind power density, lower building heights, closer proximity to streetlights, higher Source EUI, and greater emissions offsets.
4. Weighted Overlay Analysis:
    Combined normalized rasters into a single suitability model using the Weighted Overlay tool.
      Assigned weights:
      Wind Power Density: 35%
      Building Heights: 25%
      Proximity to Streetlights: 15%
      Source EUI: 20%
      Avoided Emissions: 5%.

Instrument- or software-specific information needed to interpret the data:
  Software: ArcGIS Pro 3.2.1
  Tools Used: Pairwise Intersect, Export Raster, Feature to Raster, Point to Raster, Multiple Ring Buffer, Reclassify, Weighted Overlay

Standards and calibration information, if appropriate: 
  All datasets aligned to Calgary’s boundary using geospatial clipping tools.
  Normalized datasets to ensure compatibility for Weighted Overlay Analysis.

Environmental/experimental conditions: 
  Wind power density data accounted for average conditions at 10m elevation within Calgary’s urban boundary.
  Building energy data and streetlight proximity considered typical urban infrastructure in Calgary.

Describe any quality-assurance procedures performed on the data: 
  Cross-referenced building energy data with building addresses to ensure geocoding accuracy.
  Verified wind power density raster alignment with Calgary's boundary using clipping tools.
  Checked classification thresholds for building heights and proximity buffers for accuracy.

People involved with sample collection, processing, analysis and/or submission:
  Sample Collection and Analysis: Student researcher, Nina Shafrick, is responsible for sourcing, preprocessing, and analyzing data using ArcGIS Pro.
  Data Submission and Reporting: Student researcher, Nina Shafrick, is supported by City of Calgary Open Data Portal and Global Wind Atlas documentation.



CREATIVE COMMONS LICENSE / ACKNOWLEDGEMENTS / REFERENCE SECTION

Creative Commons License

GEOG587_-_Wind_Energy_VAWT_-_Shafrick © 2024 by Nina Shafrick is licensed under CC BY 4.0 

Acknowledgements

  Contains information licensed under the Open Government Licence – City of Calgary.
  Data obtained from the Global Wind Atlas version 3.3, a free, web-based application developed, owned and operated by the Technical University of Denmark (DTU). The Global Wind Atlas version 3.3 is released in partnership with the World Bank Group, utilizing data provided by Vortex, using funding provided by the Energy Sector Management Assistance Program (ESMAP). For additional information: https://globalwindatlas.info
  "Copyright and Open Licensing" by Spatial & Numeric Data Services, University of Calgary is licensed under CC BY 4.0

Reference

  Energy Star. (2024). _The Difference Between Source and Site Energy._ ENERGY STAR. https://www.energystar.gov/buildings/benchmark/understand-metrics/source-site-difference#:~:text=Source%20Energy%20Accounts%20for%20Total%20Energy%20Use&text=Site%20energy%20may%20be%20delivered,oil%20used%20in%20onsite%20generation. 
  The City of Calgary. (2014). _Land Use Bylaw 1P2007._ https://www.calgary.ca/planning/land-use/online-land-use-bylaw.html?part=5&div=3&sec=360  
  Havre, J. (2022, October 12). _High Rise vs. Low Rise Condos: A Guide to Calgary Condo Styles._ Calgaryhomes.ca. https://calgaryhomes.ca/blog/high-rise-low-rise-condo-comparison.html#:~:text=To%20be%20considered%20a%20low,stories%20as%20a%20low%2Drise. 
