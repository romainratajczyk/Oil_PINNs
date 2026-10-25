> This repository is a fork of [ORIGINAL-REPO](https://github.com/ORIGINAL-URL) by Adrien Fabre (CIRED–CNRS). It keeps only the code I wrote during my research internship (June–September 2026), so that the original project stays untouched. I warmly thank Adrien Fabre and Léo Jean for their help throughout this work.

# Neural solvers for Markov equilibria in a dynamic oil-market game

Can "physics-informed" neural networks compute Markov-perfect (closed-loop) equilibria of a dynamic extraction game with N heterogeneous producers (cartel, oligopolists, competitive fringe, capacity constraints)?
**The short answer is no, and the report shows why.**

## Main results
- **Open loop:** the network matches the exact analytical solution (value function within 0.34%) in a two-player game.
- **Closed loop:** fails. The strategic signal ∂x_k/∂S_i (≈ 0.25 barrel at the sampling scale) is about four times smaller than the network's own policy error (≈ 0.94 barrel): no reweighting of the loss can fix this.
- **Without networks:** the Markov term vanishes under capacity saturation or perfect symmetry, grows with cost heterogeneity, dilutes as producers are added, and shifts scarcity rents by a few percent at most.

Full report (in French) in the `papers/` folder.
