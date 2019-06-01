# Gradient Descend

## Naive Idea

Often, we deal with a large amount of sample. If we stick to the analytical method, it would be either too slow or the computer simply does not have so much memory for a single calculation. For differentiable models, we take another method much faster than the analytical method. For a function of any dimensions, if we always move towards the direction of gradient, we would surely find the critical point of the function. The method follows the following steps.

1. Initialize $$W$$ holding small values or 0s.
2. Compute the gradient of $$J(W)$$ at $$\nabla J(W^t)$$ .
3. Compute the new value of W, $$W^{(t+1)}=W^{(t)}-\eta\nabla J(W^{(t)})$$ .
4. If the ending condition is satisfied, return W. If not, goto step 2.

The ending condition can be:

1. Number of iteration meets the given maximum.
2. $$J$$ varies little while $$W$$ varies. $$\frac{J(W^{(t)})-J(W^{(t+1)}}{J(W^{(t)})}\le \epsilon$$ 

## Momentum

