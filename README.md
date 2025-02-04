# Differentially Private Selection using Smooth Sensitivity

We propose the first mechanism for differentially private selection using the concept of ${\it smooth\ sensitivity}$, the Smooth Private Selection (SPS).

This page contains Python codes of our experiments on accuracy, rank error, and run time.

We pre-evaluated the value of $l$ for our mechanism in "beta_evaluation.ipynb".

In "Comparison with existing methods", we compared our SPS with two existing ${\it global\ sensitivity}$-based mechanisms (the exponential mechanism (EM) and the permute-and-flip (PF)). We also provide the results on Rank Error, which was calculated as $\mathrm{RE} = t - 1$, where $t$ denotes the true rank of the extracted data.

"Effects of gamma" provides an evaluation of suitable $\gamma$ for the SPS.

In Supplements.pdf, we provide the omitted proofs in the main paper.

## Importante Notes
This study is not specialized for any particular analysis purpose, but rather aims to enhance the basic theory and mechanisms regarding ${\it smooth\ sensitivity}$. In particular, this is the first study on private selection using ${smooth \ sensitivity}$, and we expect the research to widely expand in the future (cf. Future Directions below).  
In our experiments, we took the case of employing genome statistics as a score function for one example, and showed that the proposed method (SPS) does have the potential to provide higher accuracy than existing ${\it global \ sensitivity}$-based methods. Certainly, depending on the score function and data characteristics, ${\it global\ sensitivity}$-based methods may be superior (cf. discussion in Section V); however, in terms of increasing the possibilities for better score functions and options for differentially private selection mechanisms, this study will have a significant impact.

## Future Directions

・Developing an optimal method for determining the values of $k$ and $l$ that provide the highest accuracy for each analysis data. (This will also be important in constructing algorithms for numeric queries.)

・Conducting general theoretical analysis of our mechanism (including our methods for computing ${\it smooth\ sensitivity}$ and ${\it smooth\ upper\ bound}$ ) given the characteristics of the data, and clarifying conditions for SPS to outperform EM and PF.

・Exploring possible noise distributions with a density function other than $h(z) \propto \frac{1}{1+|z|^\gamma}$ (under $\epsilon$-differential privacy).  
e.g.) For any $k > 1$ and $l > 0$, the distribution with density $h(z) \propto \frac{1}{|z|^k + l}$ should be $\left( \frac{l^{1/k}}{2 \cdot (k-1)^{\frac{k-1}{k}}} \cdot \epsilon, \ \frac{1}{2 (k-1)} \cdot \epsilon \right)$- ${\it admissible}$. (Detailed analyses on this distribution will be provided in a separate paper.)  
← Are there any cases where $\alpha$ and $\beta$ in the ${\it admissible}$ property cannot be represented as linear functions of $\epsilon$? / Given functions $\alpha$ and $\beta$, can we find an $(\alpha, \beta)$- ${\it admissible}$ distribution?

・Developing efficient algorithms for obtaining ${\it smooth\ sensitivity}$ (not ${\it smooth\ upper\ bound}$) for any $\beta$. (And exploring the bounds of $\beta$ where ${\it smooth\ sensitivity}$ can be obtained in an efficient manner.)

・Integrating our mechanism with the joint approach [[Gillenwater et al., 2022](https://proceedings.mlr.press/v162/gillenwater22a.html)] and the local dampening mechanism [[Farias et al., 2023](https://link.springer.com/article/10.1007/s00778-022-00774-w)], while considering $(\epsilon,\delta)$-differential privacy.

・For datasets with a large $m$, there will be less advantage of our method because $\max_r S(x,r)$ (in the SPS) becomes closer to $GS_{u,\mathcal{R}}$. Using this study as a starting point, we intend to develop methods that are valuable even for large datasets.    
← Is it possible to satisfy differential privacy while adding noise of different scales for each $r \in \mathcal{R}$? (In our mechanism, the noise part is expressed by the same formula for all $r$. Can we make it $r$-dependent to improve the accuracy?)

## Note

For details of our methods and discussion, please see our paper entitled "Differentially Private Selection using Smooth Sensitivity" (https://doi.org/10.1109/IPCCC59868.2024.10850477) presented at IEEE IPCCC 2024.

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
