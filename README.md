## Separation Examples

TSP examples showing how to use separation. The first set of codes solve the subtour elimination linear program ("subtour LP"). The latter codes solve the "full" TSP using callback functions where violated inequalities are added on-the-fly.

## Subtour LP codes

First is an MCF code that doesn't use separation, but is useful for debugging purposes. 
1. [subtour_LP_via_MCF](https://github.com/AustinLBuchanan/separation_examples/blob/main/subtour_LP_via_MCF.ipynb) 

Second is a CUT model that uses inequalities of the form x(S,V\S) >= 1. Separating these inequalities reduces to a min cut problem which we solve via NetworkX. We adopt a cutting plane approach in which the LP relaxation is solved, a violated cut constraint is added, then repeat until there are no more violated inequalities.
2. [subtour_LP_via_CUT_naive_cutting_plane_method](https://github.com/AustinLBuchanan/separation_examples/blob/main/subtour_LP_via_CUT_naive_cutting_plane_method.ipynb)

Third is a Dantzig-Fulkerson-Johnson (DFJ) model that uses inequalities of the form x(E(S)) <= |S|-1. Separating these inequalities _also_ reduces to a min cut problem. 
3. [subtour_LP_via_DFJ_naive_cutting_plane_method](https://github.com/AustinLBuchanan/separation_examples/blob/main/subtour_LP_via_DFJ_naive_cutting_plane_method.ipynb)

The fourth and fifth codes exploit situations where the support graph (of the LP solution) is disconnected. Whenever this is the case, we can easily find an inequality whose violation is one. Only when the support graph is connected does it resort to solving min cut problems.
4. [subtour_LP_via_CUT_smarter_cutting_plane_method](https://github.com/AustinLBuchanan/separation_examples/blob/main/subtour_LP_via_CUT_smarter_cutting_plane_method.ipynb)
5. [subtour_LP_via_DFJ_smarter_cutting_plane_method](https://github.com/AustinLBuchanan/separation_examples/blob/main/subtour_LP_via_DFJ_smarter_cutting_plane_method.ipynb)

## TSP codes

Again, we have an MCF code that doesn't use separation, but is useful for debugging purposes. 
1. [TSP_via_MCF](https://github.com/AustinLBuchanan/separation_examples/blob/main/TSP_via_MCF.ipynb) 

# Integer separation codes

Next are codes that separate integer solutions x, including CUT and DFJ models. Because x is assumed to be integer, the separation problem reduces to finding connected components.
3. [TSP_via_CUT_integer_separation](https://github.com/AustinLBuchanan/separation_examples/blob/main/TSP_via_CUT_integer_separation.ipynb)
4. [TSP_via_DFJ_integer_separation](https://github.com/AustinLBuchanan/separation_examples/blob/main/TSP_via_DFJ_integer_separation.ipynb)

# Fractional separation codes

Then we have codes that separate (possibly) fractional solutions x, including CUT and DFJ codes that solve a min cut problem in each callback.
4. [TSP_via_CUT_naive_fractional_separation](https://github.com/AustinLBuchanan/separation_examples/blob/main/TSP_via_CUT_naive_fractional_separation.ipynb)
5. [TSP_via_DFJ_naive_fractional_separation](https://github.com/AustinLBuchanan/separation_examples/blob/main/DFJ_via_DFJ_naive_fractional_separation.ipynb)

Finally, we have CUT and DFJ codes that exploit situations where the support graph is disconnected and violated inequalities are easy to find. Min cut problems are solved only as a last resort.
6. [TSP_via_CUT_smarter_fractional_separation](https://github.com/AustinLBuchanan/separation_examples/blob/main/TSP_via_CUT_smarter_fractional_separation.ipynb)
7. [TSP_via_DFJ_smarter_fractional_separation](https://github.com/AustinLBuchanan/separation_examples/blob/main/TSP_via_DFJ_smarter_fractional_separation.ipynb)
