# SPARE-TIRE-PROBLEM  

## AIMA3e  
_init(Tire(Flat) ∧ Tire(Spare) ∧ At(Flat, Axle) ∧ At (Spare, Trunk ))_  
_Goal (At (Spare, Axle))_  
_Action(Remove(obj , loc),_  
&emsp;PRECOND: _At (obj , loc)_  
&emsp;EFFECT : _¬ At(obj , loc) ∧ At (obj , Ground ))_  
_Action(PutOn(t, Axle),_  
&emsp;PRECOND: _Tire(t) ∧ At(t, Ground ) ∧ ¬ At (Flat, Axle)_  
&emsp;EFFECT: _¬ At (t, Ground ) ∧ At (t, Axle))_  
_Action(LeaveOvernight ,_  
&emsp;PRECOND:  
&emsp;EFFECT : _¬ At (Spare, Ground ) ∧ ¬ At(Spare, Axle) ∧ ¬ At (Spare, Trunk )_  
&emsp;&emsp;&emsp;&emsp;&emsp;_∧ ¬ At(Flat, Ground ) ∧ ¬ At (Flat, Axle) ∧ ¬ At(Flat, Trunk ))_  

---
__Figure ??__ The simple spare tire problem.
