# Lab. work 07 - Latches and Flip-flops
### Preparation tasks

### Characteric equations and truth tables for D,JK,T flip-flops




![eqa](eqa.png)





| **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![rising](up.png) | 0 | 0 | 0 | Sampled and stored |
   | ![rising](up.png) | 0 | 1 | 0 | Sampled and stored |
   | ![rising](up.png) | 1 | 0 | 1 | Sampled and stored |
   | ![rising](up.png) | 1 | 1 | 1 | Sampled and stored |

   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | ![rising](up.png) | 0 | 0 | 0 | 0 | No change |
   | ![rising](up.png) | 0 | 0 | 1 | 1 | No change |
   | ![rising](up.png) | 0 | 1 | 0 | 0 | Reset |
   | ![rising](up.png) | 0 | 1 | 1 | 0 | Reset |
   | ![rising](up.png) | 1 | 0 | 0 | 1 | Set |
   | ![rising](up.png) | 1 | 0 | 1 | 1 | Set |
   | ![rising](up.png) | 1 | 1 | 0 | 1 | Toggle (=invert) |
   | ![rising](up.png) | 1 | 1 | 1 | 0 | Toggle (=invert) |

   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![rising](up.png) | 0 | 0 | 0 | No change |
   | ![rising](up.png) | 0 | 1 | 1 | No change |
   | ![rising](up.png) | 1 | 0 | 1 | Toggle (=invert) |
   | ![rising](up.png) | 1 | 1 | 0 | Toggle (=invert) |
   
   
   # D latch
   ### Task of VHDL code listing of the process p_d_latch with syntax highlighting ☻
   ```vhdl 
   entity d_latch is
    Port ( en : in STD_LOGIC;
           arst : in STD_LOGIC;
           d : in STD_LOGIC;
           q : out STD_LOGIC;
           q_bar : out STD_LOGIC);
end d_latch;

   ```
