# Differentially Private Selection using Smooth Sensitivity

We propose the first mechanism for differentially private selection using the concept of ${\it smooth\ sensitivity}$, the Smooth Private Selection (SPS).

This page contains Python codes of our experiments on accuracy, rank error, and run time.

We pre-evaluated the value of $l \cdot {\beta}$ for our mechanism in "beta_evaluation.ipynb".

In "Comparison with existing methods", we compared our SPS with two existing ${\it global\ sensitivity}$-based mechanisms (the exponential mechanism (EM) and the permute-and-flip (PF)).

"Effects of gamma" provides an evaluation of suitable $\gamma$ for the SPS.

## Future Directions

・Developing an optimal method for determining the values of $k$ and $l$ that provide the highest accuracy for each analysis data. (This will also be important in constructing algorithms for numeric queries.)

・Conducting general theoretical analysis of our mechanism given the characteristics of the data, and clarifying conditions for SPS to outperform EM and PF.

・Exploring possible noise distributions with a density function other than $h(z) \propto \frac{1}{1+|z|^\gamma}$.

・Integrating our mechanism with the joint approach [[Gillenwater et al., 2022](https://proceedings.mlr.press/v162/gillenwater22a.html)] and the local dampening mechanism [[Farias et al., 2023](https://link.springer.com/article/10.1007/s00778-022-00774-w)], while developing efficient algorithms for computing ${\it smooth\ sensitivity}$ and considering $(\epsilon,\delta)$-differential privacy.

・Is it possible to satisfy differential privacy while adding noise of different scales for each $r \in \mathcal{R}$? (In our mechanism, the noise part is expressed by the same formula for all $r$. Can we make it $r$-dependent to improve the accuracy?)

## Note

For details of our methods and discussion, please contact me.

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
