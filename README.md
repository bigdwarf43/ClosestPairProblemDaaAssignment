# Closest Pair Problem Daa Assignment

https://colab.research.google.com/drive/1lO44VgtFT7umJ2b3xaOe7CMW-E4nupWc?usp=sharing

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
8. Traverse these points, for every point if a point with distance<minD exists it will be within the minD x minD rectangle below it in the array and this rectangle will contain atmost 6 points. If it were to contain more than 6 points, it will have distance less than minD which would have been found out in the first part of the algorithm only.
9. After traversing the 6 next points for each point in the inside band array we can return the closest pair.

