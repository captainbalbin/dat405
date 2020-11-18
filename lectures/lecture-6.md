# Lecture 6 - Cluster Continuation

## Combining Clustering & Classification

It's a useful strategy when labeling is expensive, and it's started with taking a dataset with handrwritten digits.

## DBSCAN

A Densitiy-Based Spatial Clustering of Applications with noice, invented in 1996.

### Needed for DBSCAN

- A _distance_ measure (or metric, similarity), often Euclidean distance
- A number defining the meaning of _neighbor_, a scanning radius
  - Epsilon: The max distance between two points considered neighbors
- A number defining the meaning of _cluster_ (vs otlier or noise)
  - Minpts: The minimum number of points in a cluster

### Neighbors

A neighbor of a point in DBSCAN is a point that is wihtin the distance € from point p.

### Labeling Step

All points are labeled with **CORE**, **BORDER**, or **NOISE**.

#### Core Points

A core point is a point that has at least minpts neighbors.

#### Border Points

A border point is a non-core point that has at least one core-point as a neighbor.

#### Noise Point

A noise point, also called an outlier, is a non-core and non-border point.

### Clustering Steps

All core point and border points are clustered, whereas outliers will not. Start with picking a new color _c_ and an uncolored core point _p_

Put an edge between core points that are neighbors. Color those connected components with the color _c_. Also color the border points of those nodes with _c_.

Repeat until all core points and border points have been colored.

### Algorithm

1. Label all points as core, border, or noise points.
2. Eliminate noise points.
3. Put an edge between all core points that are within _Eps_ of each other.
4. Make each group of connected points into seperate cluster.
5. Assign each border point to one of the clusters of its associated core points.

### DBSCAN vs. K-means

|               | K-means                                               | DBSCAN                                                 |
| ------------- | ----------------------------------------------------- | ------------------------------------------------------ |
| Points        | Assigns all points to a cluster                       | Assign all points to a cluster except outlier          |
| Shapes        | Works best when spherical clusters                    | Works with arbitrarily-shaped cluters                  |
| Specification | Requires the number of clusters to be defined by user | Does NOT require the number of cluster to be specified |

## Hierarchical Clustering
