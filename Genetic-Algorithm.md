# GENETIC-ALGORITHM

## AIMA3e
__function__ GENETIC-ALGORITHM(_population_,FITNESS\-FN) __returns__ an individual  
&emsp;__inputs__: _population_, a set of individuals  
&emsp;&emsp;&emsp;&emsp;FITNESS\-FN, a function that measures the fitness of an individual  

&emsp;__repeat__  
&emsp;&emsp;&emsp;_new\_population_ &larr; empty set  
&emsp;&emsp;&emsp;__for__ _i_ = 1 to SIZE(_population_) __do__  
&emsp;&emsp;&emsp;&emsp;&emsp;_x_ &larr; RANDOM-SELECTION(_population_,FITNESS\-FN)  
&emsp;&emsp;&emsp;&emsp;&emsp;_y_ &larr; RANDOM-SELECTION(_population_,FITNESS\-FN)  
&emsp;&emsp;&emsp;&emsp;&emsp;_child_ &larr; REPRODUCE(_x_,_y_)  
&emsp;&emsp;&emsp;&emsp;&emsp;__if__ (small random probability) __then__ _child_ &larr; MUTATE(_child_)  
&emsp;&emsp;&emsp;&emsp;&emsp;add _child_ to _new\_population_  
&emsp;&emsp;&emsp;_population_ &larr; _new\_population_  
&emsp;__until__ some individual is fit enough, or enough time has elapsed  
&emsp;__return__ the best individual in _population_, according to FITNESS\-FN  

---
__function__ REPRODUCE(_x_, _y_) __returns__ an individual  
&emsp;__inputs__: _x_,_y_, parent individuals  

&emsp;_n_ &larr; LENGTH(_x_); _c_ &larr; random number from 1 to _n_  
&emsp;__return__ APPEND(SUBSTRING(_x_, 1, _c_),SUBSTRING(_y_, _c_+1, _n_))  

---
__Figure__ ?? A genetic algorithm. The algorithm is the same as the one diagrammed in Figure ??, with one variation: in this more popular version, each mating of two parents produces only one offspring, not two.
