The Battle of Neighborhoods (Week 1)
By Anton Ammosov
Background
Our client is a businessman from Russia, he wants to open his first restaurant in Europe. He approached me to explore potential locations for him to open his new restaurant in Oslo. He believes that in Norway can appreciate the Russian cuisine as both countries are Northern and snowy, have a common border. He wants us to analyze the market and find the best place to place a restaurant in Oslo.

Business problem
Obviously, there are many restaurants in Oslo. So we will need to find places that are not already crowded. However, we should also find areas where there are very few or no restaurants with Russian cuisine in the vicinity of a potential location. Location is unimportant for our client. He would like to have a restaurant with high pedestrian traffic every day of the week. He States that he wants to make sure it is close to the city center if possible.

Using our expertise in science and data analysis, we will provide some potentially promising locations. We will describe the advantages and disadvantages of each location so that our client can make the right decision.

Data
Based on the business challenge presented above, here are the factors that affect a potential location:

Number of existing restaurants in the area (i.e. density) Number and distance to restaurants with Russian cuisine in the area (our direct competition) The distance of the neighborhood / district from the city center Instead of using pre-defined areas in Oslo, we use regularly located locations that are centered around the city center to identify these areas. We chose the Royal Palace as our urban center for this analysis.

We will rely on the following data sources to help us make a recommendation:

Potential areas will be generated using the algorithm, and approximate addresses of these generated areas will be obtained using the TomTom reverse geocoding API
The number of restaurants and their types (e.g. Italian, Russian, Asian) as well as their location in each candidate area will be obtained using the Foursquare API
The coordinates of the center of Oslo will be obtained using the TomTom API for geocoding the Royal Palace
Foursquare Data
Foursquare classifies places (e.g. arts and entertainment, food). For our problem, we are interested in a broad category of "food" that is identified by a unique alphanumeric code. The food category contains many subcategories. From the subcategories we focus on the "Russian restaurant", which is also identified by a unique alphanumeric code. In addition, there are subcategories "Russian restaurant", such as "Blini house", "Pelmeni House". We use these unique alphanumeric codes to help us identify potential direct competitors. The categories and their alphanumeric codes are located at: https://developer.foursquare.com/docs/resources/categories.

In addition to the category and subcategories of the venue, Foursquare also stores the address of the venue. We will use the address from Foursquare and then get the location coordinates from TomTom using the reverse geocoding API.

Merging data sources
As mentioned, TomTom APIs allow us to display locations in Oslo. We start with the Oslo centre, Royal Palace, and consider an area of about 6km in each direction from that centre. This defines our boundaries for analysis. We then define equal-sized "areas" or "neighborhoods" within that boundary.

Foursquare data allows us to display restaurants within certain boundaries. We get the total number of restaurants within our specific area (and each district), as well as the number of Russian restaurants. Thus, in each equal-sized area, we can calculate the density of restaurants and the percentage of those restaurants that are our direct competitors.
