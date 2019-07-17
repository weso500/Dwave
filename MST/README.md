# Dwave
Given the un-directed graph shown in figure 1 (attached), find the MST. 

My workflow involved naming each of the edges:

A: Edge weighted 1
B: Edge weighted 2
C: Edge weighted 2
D: Edge weighted 4
E: Edge weighted 5
F: Edge weighted 6

Objective: Minimize the weight of connections

Constraint: Every node is connected to another node

Next I assigned variables:
Xi = 1 if edge is selected
Xi = 0 otherwise

Objective: min(1a + 2b + 2c + 4d +5e + 6f)
Constraint: y(a + b + c + d + e + f - 3)^2

Since it was the initial run I set the weights equal.

The MatLab script I attached solves for the QUBO function: 9-4*a-3*b-3*c-1d*+f+ 2*a*b + 2*a*c + 2*a*d + 2*a*e + 2*a*f + 2*b*c + 2*b*d + 2*b*e + 2*b*f + 2*c*d + 2*c*e + 2*c*f + 2*d*e + 2*d*f+ 2*e*f

Finally using the Python script, we see that the MST is included in one of the lowest energy states. I believe by changing the constraint constant we can guarantee the correct solution! 
