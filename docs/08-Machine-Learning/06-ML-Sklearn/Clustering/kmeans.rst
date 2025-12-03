Sklearn K-Means
=========== 

K-Means clustering algorithm using scikit-learn. K-Means falls in the general category of clustering algorithms, which partition observations into groups based on similarity without using labels.

Input
--------------
It takes in a DataFrame as input

Output
--------------
Outputs cluster centers, labels, and metrics such as inertia

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnKMeans

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - n_clusters
        - Number of Clusters
        - The number of clusters to form (Default). If 'Estimate K' is True, this value is overwritten.
      * - estimate_k
        - Estimate K
        - If True, the node will iterate through the 'Search Range' to find the best K automatically.
      * - k_search_range
        - K Search Range
        - Comma separated range (e.g., '2,15') to test for optimal K. Only used if 'Estimate K' is True.
      * - optimization_metric
        - Optimization Metric
        - The metric used to determine the best K. Silhouette seeks the Max score; Inertia seeks the Elbow.
      * - featureCols
        - Feature Columns
        - Features to be used for clustering.Leaving this empty would use all columns.
      * - init
        - Initialization Mode
        - Method for initialization: 'k-means++' for smart initialization to speed up convergence, 'random' to choose n_clusters observations at random.
      * - n_init
        - Number of Initializations
        - Number of times the k-means algorithm will run with different centroid seeds. The best output is chosen based on inertia.
      * - max_iter
        - Max Iterations
        - Maximum number of iterations for a single run of the k-means algorithm.
      * - tol
        - Tolerance
        - Relative tolerance with regards to Frobenius norm of the difference in cluster centers to declare convergence.
      * - random_state
        - Random State
        - Seed for random number generation to ensure deterministic results. Leave empty for non-deterministic behavior.
      * - algorithm
        - Algorithm
        - K-means algorithm.
      * - saveCentroidsPath
        - Save Centroids Path
        - Save Centroids as CSV




