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
   ### Listing of VHDL reset and stimulus processes from the testbench tb_d_latch.vhd file with syntax highlighting and asserts
   # VHDL code of p_reset 
   
   
   ```vhdl
   p_reset_gen : process
 begin
	 s_arst <= '0';
	 wait for 38 ns;
	 
	 -- Reset activated
	 s_arst <= '1';
	 wait for 53 ns;

	 --Reset deactivated
	 s_arst <= '0';
	
	 wait for 100 ns;
	 s_arst <= '1';

	 wait;
 end process p_reset_gen;
 
   ```
   
   
   
   # VHDL code of p_stimulus
   ```vhdl
   
   p_stimulus : process
begin
	report "Stimulus process started" severity note;
	
	s_d  <= '0';
	s_en <= '0';
	
	--d sekv
	wait for 10 ns;
	s_d  <= '1';
	wait for 10 ns;
	s_d  <= '0';
	wait for 10 ns;
	s_d  <= '1';
	wait for 10 ns;
	s_d  <= '0';
	wait for 5 ns;
	
	assert ((s_arst = '1') and (s_en = '0') and (s_q = '0') and (s_q_bar = '1'))
	report "Test failed for reset high, en low when s_d = '0'" severity error;
	
	wait for 5 ns;
	s_d  <= '1';
	wait for 5 ns;
	
	assert ((s_arst = '1') and (s_en = '0') and (s_q = '0') and (s_q_bar = '1'))
	report "Test failed for reset high, en low when s_d = '1'" severity error;
	
	wait for 5 ns;
	s_d  <= '0';
	--/d sekv
	
	s_en <= '1';
	
	--d sekv
	wait for 10 ns;
	s_d  <= '1';
	wait for 5 ns;
	
	assert ((s_arst = '1') and (s_en = '1') and (s_q = '0') and (s_q_bar = '1'))
	report "Test failed for reset high, en high when s_d = '1'" severity error;
	
	wait for 5 ns;
	s_d  <= '0';
	wait for 5 ns;
	
	assert ((s_arst = '1') and (s_en = '1') and (s_q = '0') and (s_q_bar = '1'))
	report "Test failed for reset high, en high when s_d = '0'" severity error;          
	
	wait for 5 ns;
	s_d  <= '1';
	wait for 10 ns;
	s_d  <= '0';
	wait for 10 ns;
	s_d  <= '1';
	wait for 5 ns;
	
	assert ((s_arst = '0') and (s_en = '1') and (s_q = '1') and (s_q_bar = '0'))
	report "Test failed for reset low, en high when s_d = '1'" severity error;
	
	wait for 15 ns;
	s_d  <= '0';
	wait for 5 ns;
	
	assert ((s_arst = '0') and (s_en = '1') and (s_q = '0') and (s_q_bar = '1'))
	report "Test failed for reset low, en high when s_d = '0'" severity error;
	
	--/d sekv
	
	--d sekv
	wait for 5 ns;
	s_d  <= '1';
	wait for 5 ns;
	s_en <= '0';
	wait for 5 ns;
	s_d  <= '0';

	wait for 10 ns;
	s_d  <= '1';
	wait for 10 ns;
	s_d  <= '0';
	wait for 10 ns;
	s_d  <= '1';
	wait for 10 ns;
	s_d  <= '0';
	--/d sekv
	
	

	report "Stimulus process finished" severity note;
	wait;
end process p_stimulus;
   
   ```
