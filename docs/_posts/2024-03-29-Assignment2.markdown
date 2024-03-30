---
layout: post
title:  "Assignment 2 - Group 12"
date:   2024-03-29 12:05:00 +0100
categories: jekyll update
---

<link rel="stylesheet" href="http://cdn.pydata.org/bokeh/release/bokeh-1.4.0.min.css" type="text/css" />
<script type="text/javascript" src="https://cdn.pydata.org/bokeh/release/bokeh-1.4.0.min.js"></script>
<script type="text/javascript">
    Bokeh.set_log_level("info");
</script>

# Introduction
<!-- ## Intro to dataset and preprocessing -->
The city and county of San Francisco has a [website](https://datasf.org/opendata/) containing hundreds of dataset, open to the public, in various categories ranging from film locations to fire incidents and supplier contracts. With the aim of empowering the use of data in decision making and service delivery. One of these datasets is [incident reports from the San Francisco Police Department from the 2003 to May 2018](https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-Historical-2003/tmnf-yvry/about_data). The incident report are reviewed and approved by a supervising Sergeant or Lieutenant but not every report is in there because of court orders or for administrative purposes such as active investigations. 

The data that we are going to focus on is the crime category, timestamp, registered coordinates. The PD districts were changed in 2015 so the incident district were corrected using the updated PD district coordinates given by this [geojson shapefile](https://raw.githubusercontent.com/suneman/socialdata2022/main/files/sfpd.geojson), they have similar boundaries as [this map](https://www.sanfranciscopolice.org/your-sfpd/sfpd-stations/station-finder) . Additionally incidents that were registered under 100m from police stations and county jail, found with google maps, were filtered out since they are most likely not the actual place of the incident. Coordinates of the police stations and the county jail are as follows :   
```
police_stations = {  
    "central" : (37.7985422658491, -122.41009289422135),  
    "richmond" : (37.78005373442756, -122.46439362820094),  
    "taraval" : (37.74371944264308, -122.48137855500264),  
    "university" : (37.72596139051814, -122.481670077907),  
    "ingleside" : (37.72468170701921, -122.44621331609265),  
    "bayview" : (37.72983530331985, -122.39779237517104),  
    "southern" : (37.772624504764586, -122.38946608908861),  
    "mission" : (37.763015521121886, -122.42193935269174),  
    "jail" : (37.7752941628222, -122.40454730592417),  
    "tenderloin" : (37.78377184219006, -122.41291871788926),  
    "northern" : (37.780227610466994, -122.43245712308779),  
    "park" : (37.76783599865098, -122.45522933521197)  
}
```


# Evolution of drugs/narcotics and larceny/theft in each district 
After looking through the data from each district a pattern of emerged. Incident reports of drugs/narcotics seemed to decrease in many districts at the same time as larceny/theft increased, as can be seen in the figure below. The peak for drug related incidents being between 2007 and 2010, except for Bayview, Mission and Richmond. This is likely due to the effect of [the Great Recession](https://en.wikipedia.org/wiki/Great_Recession) which has been [researched exstensively](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4730513/#:~:text=Number%20of%20persons%20with%20problematic,far%20more%20intense%20at%2088.2%25.&text=Unemployed%20men%20and%20women%20increased,employed.) where almost all European countries and the USA saw an increase in substenance usage.  
On the opposite end, the peak theft incidents is 2013 to 2017, which has often been blamed on the state of California for passing a proposition in 2014 which recategorized some nonviolent offenses from felonies to misdemeanors, such as shop lifting where the value is not exceeding $950. [A UCI study](https://onlinelibrary.wiley.com/doi/abs/10.1111/1745-9133.12378) later indicated that prop 47 might have increased larcenies in Calafornia but would need more rigorous statistical testing. This increase can be seen in the plots but more often than not it can be argued that it started earlier, in 2011. 


<!-- Both crimes have 


 where most of them also seem to have a severe turnaround in the years 2010 to 2014, which seems interesting.  -->



<!-- During this time the state of California passed two propositions, the [first one](https://en.wikipedia.org/wiki/2014_California_Proposition_47) which was passed in 2014,  recategorized some nonviolent offenses from a felony to misdemeanors, that included shoplifting and grand theft where the value doesn't exceed $950 as well as personal use of most illegal drugs within a certain weight threshold. The impact of this proposition can be 

[second one](https://en.wikipedia.org/wiki/2016_California_Proposition_64) -->
<!-- https://news.uci.edu/2018/03/07/proposition-47-not-responsible-for-recent-upticks-in-crime-across-california-uci-study-says/ -->


![Image not found](/assets/drugs_and_thefts_in_pds.jpg)

# Ratios between districts
{% include pie.html %}


Looking at the ratios between districts w.r.t. the area calculated from the geojson given above and using [2020 police disctrict populations](https://www.prisonpolicy.org/origin/ca/2020/sanfrancisco_police.html), we can see that Tenderloin almost always has most cases when taking into account population and/or area for drugs and area for theft, this tracks since Tenderloin is by far the smallest district. When looking at thefts w.r.t. population Ingleside has the majority which is kind of surprising since it is the second most populated district with more than 137 thousand people in 2020. Even more interesting is the fact that from the year 2004 to 2017 Ingleside has 1.064 theft counts per capita, which roughly equals to every single person in that district to steal once over that time period. 

# Drug incidents moving from neighborhoods 

It is very obvious that during this time period San Francisco had a significant drug problem, but how it evolves and moves through neighborhoods is quite faschinating. Looking at the South-East corner of Taraval in a neighborhoods called Ingleside heights, Oceanview and Ingleside(yes the neighborhood Ingleside is not in the Ingleside police district). We can see that during 2004 to 2010 these neighborhoods are filled with drug related incidents but then it slows down significantly over the following years and almost disappears. 


{% include assignment2_heatmap_stripped.html %}




<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />

       