# TREE-SEARCH and GRAPH-SEARCH


## AIMA4e

_Two versions, at different levels of English-like versus code-like._  

__function__ GENERIC-SEARCH(_problem_) __returns__ a solution, or failure  
&emsp;_frontier_ &larr; a queue containing one path, to the initial state of _problem_  
&emsp;_solution_ &larr; Failure  
&emsp;__while__  _solution_ can possibly be improved __do__  
&emsp;&emsp;&emsp;_parent_ &larr; pop the top path from _frontier_  
&emsp;&emsp;&emsp;__for__ _child_ __in__ successors(_parent_) __do__   
&emsp;&emsp;&emsp;&emsp;&emsp;__if__ _child_ not reached before or cost(_child_) < cost(previous path to _child_'s state) __then__  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;add _child_ to _frontier_  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;__if__ _child_ is a goal and is cheaper than _solution_ __then__  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_solution_  =  _child_  
&emsp;__return__ _solution_

__function__ GENERIC-SEARCH(_problem_) __returns__ a solution, or failure  
&emsp;_frontier_ &larr; a queue containing one path, to the initial state of _problem_  
&emsp;_reached_ &larr; { }    // _An empty  mapping of_ {state: best-path-to-state}  
&emsp;_solution_ &larr; Failure  
&emsp;__while__  _solution_ can possibly be improved __do__  
&emsp;&emsp;&emsp;_p_ &larr; pop the top path from _frontier_  
&emsp;&emsp;&emsp;__for__ _c_ __in__ _problem_.successors(_p_) __do__   
&emsp;&emsp;&emsp;&emsp;&emsp;__if__ _c_ not in _reached_ or cost(_c_) < cost(reached[_c_.state]) __then__  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_reached_[_c_] &larr; _c_  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;add _c_ to _frontier_   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;__if__ _c_ is a goal and cost(c) < cost(solution) __then__  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_solution_  =  _c_  
&emsp;__return__ _solution_

---
__Figure__ ?? In the GENERIC-SEARCH algorithm, we keep track of the best _solution_ found so far, as well as a set of states that we have already _reached_, and a _frontier_ of paths from which we will choose 
the next path to expand.
In any specific search algorithm, we specify (1) the criteria for ordering the paths in the frontier,
and (2) the procedure for determining when it is no longer possible to improve on a solution.


## AIMA3e
__function__ TREE-SEARCH(_problem_) __returns__ a solution, or failure  
&emsp;initialize the frontier using the initial state of _problem_  
&emsp;__loop do__  
&emsp;&emsp;&emsp;__if__ the frontier is empty __then return__ failure  
&emsp;&emsp;&emsp;choose a leaf node and remove it from the frontier  
&emsp;&emsp;&emsp;__if__ the node contains a goal state __then return__ the corresponding solution  
&emsp;&emsp;&emsp;expand the chosen node, adding the resulting nodes to the frontier  

---
__function__ GRAPH-SEARCH(_problem_) __returns__ a solution, or failure  
&emsp;initialize the frontier using the initial state of _problem_  
&emsp;**_initialize the explored set to be empty_**  
&emsp;__loop do__  
&emsp;&emsp;&emsp;__if__ the frontier is empty __then return__ failure  
&emsp;&emsp;&emsp;choose a leaf node and remove it from the frontier  
&emsp;&emsp;&emsp;__if__ the node contains a goal state __then return__ the corresponding solution  
&emsp;&emsp;&emsp;**_add the node to the explored set_**  
&emsp;&emsp;&emsp;expand the chosen node, adding the resulting nodes to the frontier  
&emsp;&emsp;&emsp;&emsp;**_only if not in the frontier or explored set_**

---
__Figure__ ?? An informal description of the general tree\-search and graph\-search algorithms. The parts of GRAPH\-SEARCH marked in bold italic are the additions needed to handle repeated states.
