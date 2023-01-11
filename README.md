# Best-Market-for-Verizon-5G-Home-Internet
What are the best markets for "Fixed Wireless Access" (FWA) home Internet products?
Our initial problem statement that was given was to find "What are the best markets for "Fixed Wireless Access" (FWA) home Internet products?". FWA is part of Verizon’s line of Internet service which enables Internet access using radio frequencies instead of cables. Since 5G is a new technology we are not focused so much on the specific product itself but rather on the capabilities of 5G itself.

As part of the challenge we were given:
- the type of model we should use, unsupervised clustering. Clustering is a ML technique that groups data points into a specific cluster where the data points in that cluster should share similar characteristics and properties. In unsupervised learning the algorithm uncovers hidden insights in the data for us.
- no datasets were provided to us, Digant recommended using public domain data from FCC (Federal Communications Commission) and U.S. Census.

   We consulted with our challenge advisors to better understand how we could approach this challenge:
Definition of geographical location/region (Metropolitan statistical area, city, state, census region, zip code). We decided to cluster based on zip codes since it is among the smallest out of these measures
What kind of markets to focus on (where competitors and verizon have already rolled out services, and where are people who might be interested in upgrading to 5G). Then, we decided to take a two-fold approach and determine what has already worked and replicate that, and find out 3G/4G potential customer bases to tap into.

So, we narrowed down our original problem statement to “Determine the top 10 regions we would recommend to Verizon to promote 5G products”.

From FCC database we found of interest their Fixed Broadband Deployment Data collected June and December of each year. We chose the most recent one available, June 2021, so that our data would be more current. The maximum advertised download and upload speeds from this dataset would inform us on the type of coverage customers are receiving in this area. If there were customers in a certain area that were receiving low download and upload speeds then we could make the case that they would be incentivized to upgrade to 5G.

The Ookla open source database also provided a dataset containing the average download, upload, and latency speeds. Also on the Ookla website we found an source of data that would highly relevant to our project since it showed the specific network operator providing service (from Verizon to U.S. Cellular), the city name, and coordinates. 
> Approximately 8,000 pages of code when we tried to get the entire JSONstring off the website, that is, where the data is stored. So we used Beautiful Soup library to loop over 122,000+ targets in the JSON object, removed the cities that were not part of the 50 states in the U.S., separated the U.S. city names and states into new columns, and created a function using a GeoPy library to convert the latitude and longitude coordinates to zip codes.
<img width="980" alt="Screen Shot 2023-01-11 at 4 58 52 PM" src="https://user-images.githubusercontent.com/78544539/211926751-754e116f-5e4a-411c-ba2e-d6ebbc4ba8e9.png">

From our Ookla 5G Map dataset we found that the most 5G consumers across the U.S. were using AT&T Mobility, followed by Verizon, and then by T-Mobile.

From our FCC dataset we fit the linear regression to predict correlation between download and upload speeds and understand the relationship between maximum upload and download speeds. Independent : download, dependent: upload speed. Mean absolute error is very low so yes it is overfitting, but this serves more so as intuition to understand FCC data.

Key findings: 
-When it comes to 5G services, consumers prefer T-Mobile based on the most recent weekly data 
-From average and download and upload speeds, high network speeds are not equally distributed across America
-It is possible that more R&D spending on behalf of telecommunications companies will close this inequality gap

Exploratory Data Analysis(EDA):
<img width="807" alt="Screen Shot 2023-01-11 at 4 59 15 PM" src="https://user-images.githubusercontent.com/78544539/211926824-459a5643-95a2-42b6-8037-d039d5ac1d1f.png">
Linear Regression Model: 
<img width="439" alt="Screen Shot 2023-01-11 at 5 28 34 PM" src="https://user-images.githubusercontent.com/78544539/211931566-a98528ff-71af-498d-a8a2-266641a8b03b.png">

