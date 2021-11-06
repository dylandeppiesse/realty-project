# realty-project
Scraping realty data for use in a Machine Learning personal project
This data is being scraped from the website rew.ca and the goal is to scape all data for British Columbia, Canada.

Using BeautifulSoup to perform the scraping and eventually get this into a Pandas dataframe to work on

I'm currently able to scrape data for individual regions, but due to how the website is set up I need to create a loop to go through all regions and scrape the entries within them.

There are two ways to navigate and thus two ways to scrape. Either going through the Province --> Main Cities listing, which skips many smaller regions including all of vancouver island, or the below route. I'll try to use the below route as I believe it will gather the greatest number of listings. 
The other issue with using the short route, as I'll call it, is that many of the searches expect refinement and thus hit a 25 page max, where many listings will just not be included.

The structure is as follows:
Province --> Sub-region (grouped by region) --> Neighbourhood --> Individual Listing
For example: British Columbia --> Vancouver (in the group of Greater Vancouver) --> Kitsilano --> Individual Listing

URLs follow this convention: 
https://www.rew.ca/sitemap/real-estate/bc --> https://www.rew.ca/sitemap/real-estate/vancouver-bc --> https://www.rew.ca/sitemap/real-estate/kitsilano-vancouver-bc

Steps: 

1.Get a list of all Sub Regions

2. Get a list of every neighbourhood

3. Replace "sitemap/real-estate" with "properties/areas so that the above Kitsilano url is: https://www.rew.ca/properties/areas/kitsilano-vancouver-bc

4. Start scraping
