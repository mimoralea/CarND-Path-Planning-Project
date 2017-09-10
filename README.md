# Path Planning Project
Self-Driving Car Engineer Nanodegree Program

### Final Solution

[![Alt text](https://img.youtube.com/vi/DXWyG8Gi2R8/0.jpg)](https://www.youtube.com/watch?v=DXWyG8Gi2R8)

### How it's done
   
#### The car drives according to the speed limit

Max speed is set to 49.5 mph so that there is little chance of passing the 50 mph threshold.

#### Max Acceleration and Jerk are not Exceeded

Speed is only incremented 0.5 at a time so to minimize jerk.

#### Car does not have collisions

It surely doesn't.

#### The car stays in its lane, except for the time between changing lanes

The car has a preference to stay in the middle lane per design because the middle lane has more options available for passing cars.
The car effectively stays in the middle only moving lanes to pass cars.

#### The car is able to change lanes

It does and it does it well.

### Model Documentation

The car will stay center for as long as possible. If a car in front is 20 s units away from it, it will start considering switching lanes. It will change either left or right if any of those are empty. Check lines 314 through 321. It will prefer changing to left is there is more space on the left than on the right to pass the car in front of it. Otherwise, it will prefer right. Check lines 322 through 329. Finally, it will change left if the space on the left lane is sufficient for passing the car in front, and there is more of that space on the left than the right. Otherwise, it will prefer the right. Check lines 330 through 337. If the car is on either the leftmost or rightmost lane, it will switch to the middle lane as soon as it finds clearance. Check lines 340 through 355.

The velocity is kept constant at 49.5 mph unless there is a car in front of it. In that case, the car will adjust to match the car in front's speed - 2 mph to avoid too much movement.
