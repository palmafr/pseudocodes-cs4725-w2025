# BLOCKS-WORLD-PROBLEM  

## AIMA3e  
_Init(On(A, Table) ∧ On(B, Table) ∧ On(C, A)_  
&emsp;_∧ Block (A) ∧ Block (B) ∧ Block (C) ∧ Clear (B) ∧ Clear (C))_  
_Goal (On(A, B) ∧ On(B, C))_  
_Action(Move(b, x, y),_  
&emsp;PRECOND: _On(b, x) ∧ Clear (b) ∧ Clear (y) ∧ Block (b) ∧ Block (y) ∧_  
&emsp;&emsp;&emsp;&emsp;&emsp;_(b ~= x) ∧ (b ~= y) ∧ (x ~= y),_  
&emsp;EFFECT: _On(b, y) ∧ Clear (x) ∧ ¬On(b, x) ∧ ¬Clear (y))_  
_Action(MoveToTable(b, x),_  
&emsp;PRECOND: _On(b, x) ∧ Clear (b) ∧ Block (b) ∧ (b ~= x),_  
&emsp;EFFECT: _On(b, Table) ∧ Clear (x) ∧ ¬On(b, x))_

---
__Figure ??__ A planning problem in the blocks world: building a three-block tower. One solution is
the sequence _[MoveToTable(C, A), Move(B, Table, C), Move(A, Table, B)]._  
