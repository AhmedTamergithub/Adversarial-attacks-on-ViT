# Adversarial-attacks-on-ViT
This repo explores adverarial attacks done on Vision Transformers , to study how these attention based models have specific attacks different from Convolution based Models (CNNs)

# Attack 1 ( Dual attack of first stage of Patchout , then PNA 

1: δ₀ ← 0                     # start with zero perturbation
2: α ← ε / I                  # per-iteration step size
3: for i = 0 to I−1 do
4:     x_s ← PatchOut(x_p, T)        # randomly select T patches
5:     M ← Equation 6                 # build patch-selection mask M
6:     g ← PNA(∇_δ J with L₂ norm)    # compute gradient using PNA forward
7:     δᵢ ← clip_ε(δᵢ₋₁ + α · g)      # update perturbation & keep within [−ε, ε]
8: end for
9: x_adv = x + δᴵ
10: return x_adv
