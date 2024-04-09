 [[Range searching]]
	- Strat, search the subtree rooted at $v$ only if the query rectangle $R$ intersects region($v$)
	- region($v$) $\subseteq R$ 
		- report all leaves (points) of $T(v)$
	- region($v$) $\not \subseteq R$ and region($v$) $\cap R \not = \emptyset$
		- recursively check region(lchild($v$)) and region(rchild($v$))
	- ![[kdtresearch.heic]]
#coms418 