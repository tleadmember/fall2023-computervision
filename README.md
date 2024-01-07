# fall2023-computervision
Group project in the course CSCI507 Computer Vision in Fall 2023 at the Colorado School of Mines.

Group members: Yee Shen Teoh, Thong Quoc (Bill) Huynh.

Each group of students can choose a topic for the project, with approval from the course instructor. My group opted for an algorithm to detect road lanes. This is not a novel algorithm but it demonstrates the group members' ability to understand the currently available computer vision techniques and how to combine individual techniques into a program for a specific application.

The project is completed using MATLAB. MATLAB code files are available upon requests to huynh@mines.edu.

Stage 1: drawing the boundaries of road line objects manually by finding furthest (corner) points of each block that satisfies the Area and Centroid location region property requirements, and plotting straight lines connecting the 4 corner points. Using imopen() to get rid of small blobs of noise.
–> drawing lines manually for blobs makes processing time very slow

Stage 2: drawing boundaries using bwboundaries() return values (pixels locations of boundary points),  but still only using the Area and Centroid location region property requirements to choose blobs. Using imopen() as well as imclose() to both get rid of small blobs of noise as well as filling in larger blobs. 
–> faster processing time in MATLAB

Stage 3: add more region property requirements for blobs, beyond Area and Centroid (now including Eccentricity, MinorAxisLength, Extrema, Perimeter) 
–> better performance in detecting the road lines correctly, instead of just any blobs roughly the size required

Stage 4: substituting the MinorAxisLength region property (not too distinctive of road line blobs) with the Orientation property now. As cars drive along the road lanes, the lines will only appear at angles from roughly 90 degrees with the horizontal axis (vertical on screen) to a minimum of 30 degrees with the horizontal axis (slanted).
–> reducing false positives in detecting road lines, improving detection accuracy
