# rockyIntertidal
This package contains functions that import and export views from the rocky intertidal Access database and/or CSVs that
make up the rocky intertidal data package and provides functions to query, summarize, and visualize data collected by
the Northeast Temperate Network in rocky intertidal habitats in Acadia National Park and Boston Harbor Islands National 
Recreation Area. THe R package can be installed using `pak::pkg_install('doi-nps/rockyIntertidal')`. Previous archived
versions of this R package can be found at <a href="www.github.com/katemmiller/rockyIntertidal">
www.github.com/katemmiller/rockyIntertidal</a>

This package is organized into import/export, get, summary, and plotting functions. Functions starting with "get" pull 
together data from the views and allow the user to filter by common factors, such as park, locations, years, species, etc. 
Function names that start with "sum" are higher level functions that summarize data and typically have group_by and 
summarize functions under the hood. Function names starting with "plot" are plotting functions that typically return a 
ggplot object. In general, each view in the data package has a get function, and may have a summary and/or plotting function.
A tutorial website for this R package can be found at <a href = "doi-nps.github.io/rockyIntertidal">doi-nps.github.io/rockyIntertidal</a>.

Note a companion repo of R Markdown reports for summarizing and QA/QCing data can be found at: doi-nps/rockyIntertidal_reports.

This package contains the following functions: 
<ul>
<li>importData: imports views from the rocky intertidal data package either as csvs or views in the MS Access database.</li>   
<li>exportData: exports views as csvs in a zip file for easier import and transfer.</li>  
<li>importWaterTemp: imports compiled water temperature at high tide data.</li>  
<br>
<li>getEvents: queries sample event data.</li>
<li>getBolts: queries bolt location data, which are higher level than event data.</li>
<li>getBarnacleRecruitment: queries barnacle recruitment data.</li>  
<li>getBirdsMammals: queries birds and mammals observed during sample events.</li>                        
<li>getEchinoCounts: queries echinoderm count data.</li>         
<li>getEchinoMeas: queries echinoderm measurement data.</li>
<li>getMotileInvertCounts: queries motile invertebrate counts.</li>   
<li>getMotileInvertMeas: queries motile invertebrate measurements.</li>     
<li>getPhotoCover: queries photoplot cover data by community type and species.</li>          
<li>getPIBoltDistance: ties together point intercept distance, bolt distance, and elevation along the three transects.</li>
<li>getPISpecies: queries point intercept species detections data by transect.</li>
<li>getSppConditions: queries condition of species of concern detected during monitoring.</li>
<br>
<li>sumBarnacleRecruitment: summarizes plot-level median, min and max counts of barnacles per site by summer or winter plots.</li>  
<li>sumEchinoCounts: summarizes echinoderm counts per site, visit, and species.</li>         
<li>sumEchinoMeas: summarizes echinoderm measurements per site, visit, and species.</li>          
<li>sumMotileInvertCounts: summarizes motile invertebrate counts per site, visit, species, and damage.</li>   
<li>sumMotileInvertMeas: summarizes motile invertebrate counts per site, visit, species, and 5cm size class.</li>     
<li>sumPhotoCover: summarizes site-level photoplot cover by community type and species. </li>           
<li>sumPISpecies: relates bolt distance, point intercept distance, and species detection.</li>      
<br>
<li>plotBarnacleRecruitment: plots median site-level barnacle counts plot min/max count per site and year. Defaults to only count summer plots.</li> 
<li>plotBuoyData: plots water temperature and buoy data at high tide by site. Must import the compiled logger data for this to work.</li>           
<li>plotEchinoCounts: plots average count by species with upper 75% and lower 25% distribution as error. </li>        
<li>plotEchinoMeas: plots a heat map of counts within 1mm size increments for echinoderms.</li>          
<li>plotMotileInvertCounts: plots average count by species with upper 75% and lower 25% distribution as error.</li>  
<li>plotMotileInvertMeas: plots a heat map of counts within 1mm size increments for motile invertebrates. </li>   
<li>plotPhotoCover: plots average cover by species, community type and year either as points or heat map.</li>          
<li>plotPISpecies: plots site-level species detections by elevation and year.</li>           
<li>plotPITransects: plots transect contours for each year based on bolt and point intercept data. </li>         
<li>plotSpeciesContours: plots a loess smoothed contour averaging the transects across all years with
point intercept detections overlaid for each year and photopoint cover as pie charts close to the elevation
they are located relative to the transects.</li>    
<li>plotWaterTemp: plots water temperature at high tide by site using compiled temperature logger data.</li>   
<br>
<li>theme_rocky: ggplot2 theme specific to the rockyIntertidal package</li>   
</ul>