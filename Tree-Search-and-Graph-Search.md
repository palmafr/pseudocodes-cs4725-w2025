# TREE-SEARCH and GRAPH-SEARCH

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
