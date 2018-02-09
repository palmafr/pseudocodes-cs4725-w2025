# AIR CARGO PLANNING PROBLEM  

## AIMA3e  
_Init(At (C 1 , SFO) ∧ At (C 2 , JFK ) ∧ At(P 1 , SFO) ∧ At (P 2 , JFK )_  
&emsp;_∧ Cargo(C 1 ) ∧ Cargo(C 2 ) ∧ Plane(P 1 ) ∧ Plane(P 2 )_  
&emsp;_∧ Airport (JFK ) ∧ Airport(SFO))_  
_Goal (At(C 1 , JFK ) ∧ At(C 2 , SFO))_  
_Action(Load (c, p, a),_  
&emsp;PRECOND: _At(c, a) ∧ At (p, a) ∧ Cargo(c) ∧ Plane(p) ∧ Airport(a)_  
&emsp;EFFECT: _¬ At (c, a) ∧ In(c, p))_  
_Action(Unload (c, p, a),_  
&emsp;PRECOND: _In(c, p) ∧ At (p, a) ∧ Cargo(c) ∧ Plane(p) ∧ Airport(a)_  
&emsp;EFFECT: _At(c, a) ∧ ¬ In(c, p))_  
_Action(Fly(p, from, to),_  
&emsp;PRECOND: _At(p, from) ∧ Plane(p) ∧ Airport(from) ∧ Airport(to)_  
&emsp;EFFECT: _¬ At (p, from) ∧ At(p, to))_  

---
__Figure ??__ A PDDL description of an air cargo transportation planning problem.
