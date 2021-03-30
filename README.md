# # Lab. work 07 - Latches and Flip-flops
# Preparation tasks

| **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![up](images/up.png) | 0 | 0 | 0 | Sampled and stored |
   | ![rising](images/up.png) | 0 | 1 | 0 | Sampled and stored |
   | ![rising](images/up.png) | 1 | 0 | 1 | Sampled and stored |
   | ![rising](images/up.png) | 1 | 1 | 1 | Sampled and stored |

   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | ![rising](images/up.png) | 0 | 0 | 0 | 0 | No change |
   | ![rising](images/up.png) | 0 | 0 | 1 | 1 | No change |
   | ![rising](images/up.png) | 0 | 1 | 0 | 0 | Reset |
   | ![rising](images/up.png) | 0 | 1 | 1 | 0 | Reset |
   | ![rising](images/up.png) | 1 | 0 | 0 | 1 | Set |
   | ![rising](images/up.png) | 1 | 0 | 1 | 1 | Set |
   | ![rising](images/up.png) | 1 | 1 | 0 | 1 | Toggle (=invert) |
   | ![rising](images/up.png) | 1 | 1 | 1 | 0 | Toggle (=invert) |

   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![rising](images/up.png) | 0 | 0 | 0 | No change |
   | ![rising](images/up.png) | 0 | 1 | 1 | No change |
   | ![rising](images/up.png) | 1 | 0 | 1 | Toggle (=invert) |
   | ![rising](images/up.png) | 1 | 1 | 0 | Toggle (=invert) |
