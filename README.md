## Galaxy classifier 

This is a project to classify galaxies into the following three types using Galaxy Zoo data
1. Spiral 
2. Elliptical 
3. Merger

The classification was done using 
1. Decision tree with ~80% accuracy
2. Random forest classifier with ~87% accuracy

The features used were color indices, eccentricity, adaptive moments and concentration. Concentration was taken as the ratio of the radii containing 50% and 90% of the Petrosian flux.

# Update

galaxy_zoo.ipynb is an appraoch to classify galaxies into 37 type using a deep CNN

The original data is pre-processed in the following ways:
1. The meatier part of the data is in the center of the image. The deep space surrounding the galaxy won't help classify them, so I cropped the original image from 424x424 to 256x256 and downscaled it to 64x64.
2. I applied a random rotation on the image by an angle in [0, 360].
3. The image is zoomed by a randomly selected value in the array [1.3, 1.2, 1.1, 1, 1/1.1, 1/1.2, 1/1.3]
4. The image was flipped using both horizontally and vertically by a two coin toss (Eg: An HH outcome would mean the image is flipped both horizontally and vertically, while a HT outcome would mean a horizontal flip but not a vertical flip). 

The CNN resulted in an RMSE ~ 0.098. 

