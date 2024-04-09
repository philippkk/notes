#coms418 
-  #### [[Trapezoidal Map]]
	- maps point location query easier
		- needs $O(n)$ storage
		- general assumption - no two points will have same x coordinate
			- draw a rectangle bounding,$R$, all segments in its interior
			- from every point draw two vertical extensions (up and down)
			- stop when they meet another segment or the boundary of $R$
		- ##### Face of a trapezoidal map
			- trapezoid, triangle
			- every face in $T(s)$ has $\geq 2$ vertical sides and 2 non-vertical sides
			- a vertical side is one of two cases:
				- a vertical extension, or
				- a vertical edge of $R$
			- # yan bin likes the figures 
		- ##### Top & bottom
			- distinguish the two non-vertical sides.
			- ###### classification of the left side
				1. degenerating into a point
				2. lower vertical extension (top vertex to bottom line)
				3. upper vertical extension (bottom vertex to bottom line)
				4. upper and lower extension (vertex in the middle of line)
				5.  left edge of $R$ 
			- ###### Defining endpoint
				-  leftp($\Delta$) = left endpoint of top($\Delta$)
				- or left endpoint of bottom($\Delta$)
				- or both 
				- or right endpoint of a $3^{rd}$ segment
				- or lower right corner of $R$
				- rightp($\Delta$), is similar
		- ##### complexity of the trapezoidal map
			- ###### Lemma 1. $T(s)$ contains $\leq 6n + 4$ vertices
				- ==proof.== a vertex is one of three types:
					- a vertex of $R$                                  
						- 4
					- an endpoint of a segment          
						- $\leq 2n$
					- the point where the vertical extension line starting in an endpoint reaches another segment or the boundary of $R$ 
						- every endpoint generates at most two such points
						- $\leq 2 \times 2n$
					- vertices $\leq 4+2n+4n = 6n + 4$
			- ###### Lemma 2. $T(2)$ contains $\leq 3n +1$ trapezoids
				- ==proof.== every trapezoid $\Delta$ is represented by leftp($\Delta$). Need only count leftp($\Delta$), including multiplicities (times for each endpoint) 
				- leftp($\Delta$)is one of three possible types:
					- lower left corner $R$
						- it is leftp($\Delta$) for exactly 1 trapezoid
					- right endpoint of a segment ($n$ such points)
						- it is leftp($\Delta$) for $\leq 1$ trapezoid (shared endpoint)
					- left point of a segment ($n$ such points)
						- leftp($\Delta$) for $\leq 2$ trapezoids (shared endpoint)
					- num trapezoids $\leq 1 + 1 \times n _ 2 \times n = 3n + 1$ 
			- ###### Adjacency
				- trapezoids $\Delta$ and $\Delta$' are adjacent if they share a vertical edge
				-  a trapezoid has $\leq 4$ neighbors under the general position assumptions
				- $\Delta$' adjacent to $\Delta$ along the left vertical edge of $\Delta$
					- top($\Delta$) = top($\Delta$') or
					- bottom($\Delta$) = bottom($\Delta$')