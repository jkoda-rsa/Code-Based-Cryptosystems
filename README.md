# Machine Learning-Based Attacks on Code-Based Cryptosystems
*This was the master project with Daniel Baur, supervised by Professor Anna-Lena Horlemann.*

## Problem
This project presents a methodology for using machine learning to attack code-based cryptosystems. It focuses on the syndrome decoding problem, utilizing a linear code `C` of length `n` and dimension `k` over `F_q`. The parity check matrix `H` is of size `(n-k) x n` over `F_q`. For a received message `m = c + e` where `c ∈ C` and `e ∈ F_q^n` with Hamming weight `wt(e) ≤ (d-1)/2`, the goal is to find `e` given `H` and the syndrome `s`. This problem is critical to the security of the McEliece cryptosystem. 

## Methodology
The machine learning approach involves training a model as a binary multi-label classification problem to predict the error vector from a syndrome vector. The architecture includes an input layer, multiple hidden layers (using ReLU and sigmoid activation functions), and an output layer. The research showed that even a 1% success rate in decoding error vectors could potentially compromise the security of cryptosystems.

<p align="center">
    <img align="center" alt="Descriptors" src="https://github.com/jkoda-rsa/Code-Based-Cryptosystems/blob/main/img/result.png" width=80% height=80%>
    <p align="center">$\texttt{predskite}$: Prediction of novel charge transport layers for efficient perovskite solar cells</p>
</p>

## Results
We initiated model training on smaller codes with \( n=50 \) and progressively increased the size to the computational limit. Experiments on random linear binary codes (RLC) with \( n \) length and \( k=n/2 \) dimension revealed that even at \( n=1000 \), matching McEliece's original recommendation, the model could decode 1% of error vectors. This indicates a potential vulnerability in cryptosystems using such codes as public keys, questioning their security.


