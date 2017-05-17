# Purdue-UNAL Gold IronHacks 2017
<b>Name of application: </b> Chicago's Home Searcher

<b>Author: </b> David Eduardo Hormaza Herfaoui. Universidad Nacional de Colombia.

<b>Keywords: </b>  rental places, safety, affordability, traffic, students, University of Illinois.

<b>Description of the datasets and function desing </b> <br>
<ul>
<li type="disc">Climate Data Online: I could not use this dataset for lack of documentation to obtain responses with data that could be processed and used as useful information for the user (for example in JSON format, as I did with the other datasets). I tried making requests in several ways, but it was not possible to get the data I was looking for.</li>
<li type="disc">Police Stations[https://catalog.data.gov/dataset/police-stations-3a3a8]: Data type: JSON File. Columns used: latitude, longitude, name, address, website, phone, fax, TTY, zip. This dataset will be used to perform searches of the rental sites according to their proximity to police stations (to offer the user a search parameter that takes into account the relative security of the site to rent).</li>
<li type="disc">Crimes since 2017 [https://data.cityofchicago.org/Public-Safety/Crime-since-2017/itbm-jtnw]: Data Type: JSON File. Columns used: latitude, longitude, case number, primary type, description, location description. The information provided by this dataset will be used to support searches of rental sites according to their security level. Taking into account the proximity of rental sites with places where crimes have been committed, the application will establish sites that offer greater security for users.</li>
<li type="disc">Chicago Traffic Tracker - Congestion Estimates by Regions [https://catalog.data.gov/dataset/chicago-traffic-tracker-congestion-estimates-by-regions-a7daf]: Data Type: JSON File. Columns used: latitude(south), latitude(north), longitude(west), longitude (east), name, description, current speed, last update. Traffic congestion estimates will be used to determine which rental sites are connected to the best traffic routes in Chicago so that the user can choose, in terms of transportation and traffic, the most convenient place to live.</li>
<li type="disc">Parks - Locations [https://data.cityofchicago.org/Parks-Recreation/Parks-Locations/wwy2-k7b3]: Data Type: JSON File. Columns used: latitude, longitude, park name. The data provided by this dataset will be used to determine the number of parks near a renting option according to defined parameters.</li>
</ul><br>

<b>Brief description of the project </b><br>
The main goal of this project is to develop a website that allows students of the University of Illinois who just arrived in the city of Chicago to find a safe and economical place to live during the course of their university career. Although the priority areas to guide the user in choosing the place of rent are safety in the city and economic affordability, aspects such as sites that offer fun and recreation in Chicago, like parks, and the speed of traffic in the city will also be taken into account to find the most suitable rental place for the user. The site will integrate a user-friendly graphical interface, allowing effective interaction between him and the site. The sources of information on the site will be datasets with open data provided by the US government. Through the processing of this information, results will be dynamically displayed, with which the user has the possibility to interact to make a correct decision about his/her future home.<br>

<b>Map View </b><br>
<ul>
<li type="disc">Initially, a map centered on the location specified in the project instructions (Department of Computer Science, University of Illinois, Chicago, with coordinates: 41.8708 N, 87.6505  W) is shown at the starting point for the user searches. </li>
<li type="disc">All the maps used in the mashup website use markers to display the rental sites on the map, depending on the search made, the markers are different.</li>
<li type="disc">All the markers have labels that contain the respective address of each rental site offered to the user.</li>
<li type="disc">All the markers on the maps have infoWindows that show a summary of all pertinent information about rental sites in an organized, clear manner and with eye-catching visual elements.</li>
<li type="disc">The map will display markers that show rental sites based on their affordability or security. The icons that have markers in each case have a distinctive color.</li>
<li type="disc">To provide a better visualization of data to the user, when searching for rental sites according to their level of security or price, there is a button that allows to show on the map the traffic zones of Chicago, each zone has a representative color ( According to the estimated average speed there) and offers a simple animation of a pointer passing through the zone faster or slower according to the speed named above.</li>
</ul><br>


<b>Data Visualization </b><br>
The application uses a bubble chart (from a D3 library) to give the user a clear and detailed view of the characteristics of the rental sites. The user can interact with this graphic since its components offer animations. The graph also allows to orient the user in a very direct way in his/her choice of his/her next home.
<br>

<b>Interaction Form </b><br>
The user can interact with buttons or selection fields to perform the search of rental places. In the index of the page there is a button that allows to display all available rental sites. In addition there is a field that allows choosing the parameter preferred by the user to select his home. A button linked with this one redirects the user to another window, in which it's possible to choose the number of rental sites that shows the map according to one of the two aspects and apply different filters related to the distance to the University of Illinois, Police stations and parks, and traffic speed in the area. The user can search in various ways from the selection fields and search buttons. The user can choose to show or hide the traffic zones on the map.
<br>

<b>Test Case </b><br>
The application works fully in browsers: Chrome, Firefox and Edge. For the IE browser case, there are some variations on the style or some elements of the site are not shown. On Safari, an alert appears announcing that the browser does not accept the video tag used to display the content at the beginning of the site.
There are some inconsistencies in the adaptive design of the site, reducing the size of the browser window. Although I modified the code to use a scroll-bar when the window has a size smaller than the original (1270px) some elements are cluttered or remain on others. The bubble chart can not be displayed in the GitHub repository used as the host for the application.
<br>

<b>Additional information </b><br>
The <b>index.html</b> file shows the basic structure and interface of the site. Initially, a header with the name of the site and a video allusive to the city of Chicago appear, and then it is sought to introduce the user to the functionality of the application, with a very simple and understandable language. As the visual component is very important for the interaction of the user with the site, it seeks to achieve a balance between the aesthetics and design of the site and the other elements.
At the end of the file is placed a map that indicates the initial position required and to the side appear some instructions for the user to start the search of his place to rent, through a dropdown field and a search button. The entire process of searching and outputting results is explained in detail to the user through the content of the page. All actions performed by the interaction elements in the application are commanded by specific functions that take the open data provided by the datasets, and through the processing of the same, allow the user to perform very precise searches to find the rent site more appropriate. On the home page it is also possible to find a random rental site by clicking on a button, this activates several subsequent actions, and allows the user to view the bubble chart and detailed information regarding a rental site.
<br>
<b>Important </b><br>
To work with the rental sites available in Chicago for the user, I created a JSON-type file from the information provided by the Zillow API. Manually, I filtered rental sites in Chicago with parameters that seek to satisfy the need for affordability required by the user. Then, I added one by one the data of the rent sites in a 2-level data array, which consists of the following structure for each element: [latitude,longitude,property manager,address,rent price,number of bedrooms, number of baths, Square feet, phone]. In this way I can manipulate all the necessary data to help find the user the most convenient rental site, by analyzing the data. There are about 100 rental sites available to help a student at the University of Illinois to find a home in Chicago.<b> To have access to the complete functionality and styles of the mashup it should be downloaded locally.</b>


<br>
<b>References </b><br>
The video used at the beginning of the site was taken from: https://www.youtube.com/watch?v=Afsv_I0FAyY from the Youtube channel https://www.youtube.com/channel/UC8t5dLbQ4ovjlE9PTdWXbXw.
QUERY FOR SEARCH SITES IN ZILLOW:
https://www.zillow.com/homes/for_rent/Chicago-IL/1_fr/0_fs/apartment_duplex_type/17426_rid/1-_beds/1.0-_baths/133301-399902_price/500-1500_mp/250-590_size/paymenta_sort/42.104845,-87.292557,41.562545,-88.171464_rect/X1-SS1w6g1zc9ch53f_axb7v_sse/




