# CarND-Path-Planning-Project
Self-Driving Car Engineer Nanodegree Program

## Model Documentation

The implemented solution largly resembles the project walkthrough lession. The model will drive the car to target speed of 49.5 mph unless it detects a car in front.

The model constantly monitors nearby cars in the current lane, left lane and the right lane and determines whether it needs to either:

- Slow down
- Move to the left lane
- Move to the right lane

#### Slow down
If there is a car in front, and unable to switch lanes because there are other cars either in front or behind in the neighbouring lanes. The model will reduce the target speed to minimum of 0.5 mph below the speed of the car in front.

#### Move to the left lane
If there are no other cars in the left lane within +/- 30 meters in the s direction front and behind the car, the model will flag that left lane is free to switch into. Switching to left lane is preferred over right lane as usually it is the fast lane when driving on the right hand side of the road.

#### Move to the right lane
If there are no other cars in the left lane within +/- 30 meters in the s direction front and behind the car, the model will flag that left lane is free to switch into. If the right lane is also not free then the car will choose to slow down.

### Path planning
A path is mapped based on current position, previous position and three waypoints 30 meters, 60 meters and 90 meters in front. The mapping is done using cubic spline as taught during class. The spline calculation was changed slightly to apply my own understanding.