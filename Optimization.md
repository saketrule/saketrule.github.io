# Overview of Optimization problems


## Least square problem
```
minimize Sum_i (a_i^t * x - b_i)^2
```
LSP can be solved efficiently, when the matrix is full rank. Then, we can prove that the vector has to satisfy the equation (A^t * A)* x = A^t * b
[(proof)](https://www.cse.iitk.ac.in/users/rmittal/prev_course/s14/notes/lec1.pdf!)

Common variants inclue, weighted LSP, and adding regularization.


## Linear programming
Linear objective with constraint functions.
Several known methods to solve,
- [ ] Simplex
- [ ] Ellipsoid
- [ ] Interior point method


## Convex Optimization
An easier subset of the problem because of a single property - 
``` A local minimum must be a global minimum ```


### Classic problems & Stuff to know
**Chebyshev approximation**
```
min_x max_i |a_i^t * x - b_i|
```
It can be formulated as a linear program [(link)](https://www.cse.iitk.ac.in/users/rmittal/prev_course/s14/notes/lec2.pdf!)


**Cook-Levin theorem**
Boolean satisfiability problem is NP-complete. BSP is of course, a simple case of ILP, where the variables are constricted to 0-1.

**Introducing slack variables**
Standard method to convert a problem to the standard form.



## Integer programming
Optimization problems where all or some variables are restricted to be integers. Known to be NP-complete. 

```
-- IP

maximize		c^t * x
subject to 		Ax <= b,
				x >= 0,
				x belongs to Integer set (Z)

-- MIP

maximize		c^t * x
subject to 		Ax + s = b,
				s >= 0,
				x >= 0,
				x belongs to Integer set (Z)

```

- Integer linear programming (ILP) : Where the objective function & constraints are linear
- Mixed-integer programming (MIP) : Some decision variables are not discrete

```
maximize		c^t * x
subject to 		Ax <= b,
				x >= 0,
				x belongs to Integer set (Z)
```





## Mixed Integer programming



## Constraint optimization or Constraint programming (CP)
Feasibility of a solution



## Tools for solving optimization problems
**cvxpy** 
- for convex optimization problems
- Transforms the problem into standard form
- Calls a solver & unpacks the results


https://www.cvxpy.org/tutorial/index.html
Tutorial - 
1. Introduction, Basics & Syntax
2. Concepts 1 + Solving basic problems
3. Concepts 2 + Solving problems
4. Wrap up



### References
- [ ] https://medium.com/google-or-tools/google-or-tools-a-guide-39f439a5cd0f
- [ ] 
