### SITE DESCRIPTION
For this assignment we downloaded the Water Boundary Dataset for region 10 located in Colorado (specifically watershed 101900050406). This watershed covers most of city of Boulder, plus some of the foothills to the west of Boulder and some of the area south of Boulder. I wanted to pick something a little more Urban than the previous land classifcation assignment that practiced land classification on the Mississiippi Delta. This area contains grasslands, creeks, pine forests, large rock formations, and urban enviornments. Please note that I was unable to figure out how to load in satellite imagery under my watershed boundary so I used OpenStreetMap (OSM)

<img 
  src="img/boundary.png" 
  alt="Site Map" 
  width="50%">
  
#### Citations:  
Boulder, C. (n.d.). Ecology and ecosystems of the Boulder Creek watershed. Boulder Creek Watershed. https://bcn.boulder.co.us/basin/learning/ecology.html#:~:text=Ecosystems%20found%20in%20the%20Boulder,tundra%20and%20the%20aquatic%20ecosystem.

### SILHOUETTE AND ELBOW PLOTS

<img 
  src="img/silhouette_elbow.png" 
  alt="Silhouette and Elbow" 
  style="max-width:100%; height:auto; display:block; margin-left:auto; margin-right:auto;">

In order to help determine the number of clusters I wanted to use in my K means calculation I used a combination of the Elbow Method and a Silhouette Score. For the Elbow Method I calculated and plotted the within-cluster sum of squares (WCSS) or inertia, as it is know in the Sklearn package, against different values of K, and then visually identified the "elbow" on the plot where the rate of decrease sharply changes and begins to flatten out, which is somewhere around 6 or 7 clusters. For the Silhouette Score I looked for values that were closer to one, which represented a more dense and well-separated cluster. There seems to be a dip in the siloutte score at 4, which is interesting to see. However, they seemed to trail off closer and closer to 1 - so I went with 6 clusters in an attempt to get discrete land classification groups, while also trying not to over classify the data. 

### RGB AND CLUSTER PLOTS
<img 
  src="img/rgb_boulder.png" 
  alt="RGB" 
 width="90%">
<img 
  src="img/clusters_boulder.png" 
  alt="RGB" 
  width="75%">
  
  I plotted both the RGB color bands (after they had been brightened and saturated) and the K means clusters to see how they visually compared. It looks like the K means clusters were able to cluster together more open farm area, roads, and it seems to follow elevation changes - but it is hard to tell how accurate it is exactly without trained data or a more interactive map/information about the area. I believe the unnatural bright colors present in the rgb image to be NaN values. I was able to drop the NaN values prior to classifying the K means clusters but I ran into some coding errors when trying to drop the NaN values from the RGB image.
