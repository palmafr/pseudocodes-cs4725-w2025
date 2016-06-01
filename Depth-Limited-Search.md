# DEPTH-LIMITED-SEARCH

## AIMA3e
__function__ DEPTH-LIMITED-SEARCH(_problem_,_limit_) __returns__ a solution, or failure/cutoff  
&emsp;__return__ RECURSIVE\-DLS(MAKE\-NODE(_problem_.INTIAL\-STATE),_problem_,_limit_)  

__function__ RECURSIVE\-DLS(_node_,_problem_,_limit_) __returns__ a solution, or failure/cutoff  
&emsp;if _problem_.GOAL-TEST(_node_.STATE) __then return__ SOLUTION(_node_)  
&emsp;__else if__ _limit_ = 0 __then return__ _cutoff_  
&emsp;__else__  
&emsp;&emsp;&emsp;_cutoff_\__occurred?_ &larr; false  
&emsp;&emsp;&emsp;__for each__ _action_ __in__ _problem_.ACTIONS(_node_.STATE) __do__  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_child_ &larr; CHILD\-NODE(_problem_,_node_,_action_)  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_result_ &larr; RECURSIVE\-DLS(_child_,_problem_,_limit_\-1)  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;__if__ _result_ = _cutoff_ __then__ _cutoff_\__occurred?_ &larr; true  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;__else if__ _result_ &ne; _failure_ __then return__ _result_  
&emsp;&emsp;&emsp;__if__ _cutoff_\__occurred?_ __then return__ _cutoff_ __else return__ _failure_  

---
__Figure__ ?? A recursive implementation of depth\-limited tree search.
