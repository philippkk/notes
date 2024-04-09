#coms418 
- #### Simple data structure 
		- draw vertical lines through all the vertices
		- sort by x-coordinate
		- determine the slab containing $q$
			- $O(logn)$
		- ##### Slab:
			- no vertices inside a slab
			- bounded by the vertical lines through two adjacent vertices in the sorted list.
			- edges don't cross each other.
			- order from top to bottom
				- store edges intersecting a slab in sorted order (in an array)
				- label each edge with the face immediately above
		- ##### Query Algorithm
			1. Determine the slab containing $q$
				-  binary search with x-coordinate of $q$ ($O(logn$))
			2. Binary search within the slab
				-  given a segment $s$ crossing the slab, determine whether $q$ is above, below, or on $s$.
				-  $\geq n$ segments $\rightarrow O(logn)$ time 
			- Query time is $O(logn)$ 
		- ##### Storage
			- an array on x-coordinate of vertices $O(n)$
			- an array for every slab $O(n)$
				- $O(n)$ slabs
				- $O(n^2)$ in worst case (possible)
			- $\Theta(n^2)$ storage