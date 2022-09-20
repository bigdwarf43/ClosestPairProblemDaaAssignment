# Closest Pair Problem Daa Assignment

### Name - Yash Wankhedkar
### Roll no- 77

#### Use the colab file to run the program and generate the plots
https://colab.research.google.com/drive/1lO44VgtFT7umJ2b3xaOe7CMW-E4nupWc?usp=sharing

#### Requirements for running the closestPairA77.py file - Numpy, Matplotlib

## Question: 
Implement a solution to find a minimum distance between two points.
Input array: each element defined as [a,b] for example [2,3]
Use distance formula.

## Approach:
1. A set of points are given on a 2D plane with X and Y axis, we have to find the closest pair of points
2. Sort the points on the basis of X co-ordinate, and find the mid point.
3. Recursively find the closest pair on the left of mid point and their distance(minD1) and find the closest pair on the left of mid point and their distance(minD2)
4. We have to consider the possiblity that the closest pair can be made up of one point on the left part and one point on the right part
5. Find the minimum between minD1 and minD2 (minD)
6. If a closest pair exist other than minD1 and minD2 it will lie on a band that spans for minD distance from the midpoint, if one of them is outside the band then distance between them will always be greater than minD. We need to traverse the points that are inside the band only.
7. Sort the points in the band according to the Y co-ordinate.
8. Traverse these points, for every point if a point with distance<minD exists it will be within the minD x minD rectangle below it and this rectangle will contain atmost 6 points(All of these points will be below the current point, not considering the upper points as they are already considered as we are traversing from top to bottom). If it were to contain more than 6 points, it will have distance less than minD which would have been found out in the first part of the algorithm only.
9. After traversing the 6 next points for each point in the inside band array we can return the closest pair.

## Complexity:

  1. Sorting of X and Y values takes O(nlogn)
  1. Splitting of X sorted and Y sorted values takes n time
  2. T(n/2) for the recursive call for the left part and T(n/2) for the right part
  3. n time for finding the points that are in the band 
  4. 6n for checking the six points in the band for every point

The complexity of the algorithm is O(nlogn)

## Test Cases:

### Test case 1: (2, 3), (12, 30), (40, 50), (5, 1), (12, 10), (3, 4)

Closest pair:
Point1: (2, 3), Point2: (3, 4)

Distance between point1 and point2: 1.4142135623730951

![testCase1](https://user-images.githubusercontent.com/62785185/191300909-e60b22c6-969b-425d-9f4f-4fbcb0bf8ce1.png)


### Test case 2: (20, 4), (9, 8), (5, 10), (4, 4), (2, 0), (18, 21)
Closest pair:
Point1: (2, 0), Point2: (4, 4)

Distance between point1 and point2: 4.47213595499958


![testCase2](https://user-images.githubusercontent.com/62785185/191301464-9ebdc92d-edce-41f8-92da-d8e9a1e14cef.png)

### Test case 3: (-2,3), (3,2), (5,6), (7,8), (-5,-2), (-7,-6), (4,5), (6,3)
Closest pair:
Point1: (4, 5), Point2: (5, 6)

Distance between point1 and point2: 1.4142135623730951

![testCase3](https://user-images.githubusercontent.com/62785185/191302879-ed78abd0-9d08-4e90-986e-6a1f32931312.png)


