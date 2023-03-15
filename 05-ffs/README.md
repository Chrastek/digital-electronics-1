# Lab 5: Jakub Chrastek

### D & T Flip-flops

1. Screenshot with simulated time waveforms. Try to simulate both D- and T-type flip-flops in a single testbench with a maximum duration of 200 ns, including reset. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

  ![332910337_737840924418286_3975513889511193009_n](https://user-images.githubusercontent.com/124879589/225343726-d4d896cc-8ae7-438e-a4ab-140b54e234b7.png)


### JK Flip-flop

1. Listing of VHDL architecture for JK-type flip-flop. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture behavioral of t_ff_rst is
    signal s_q : std_logic;
begin

    p_t_ff_rst : process (clk)
    begin
        if rising_edge(clk) then
            if (k = '0') then
               if (j = '1') then
                  s_q  <= '1';
               end if;
            else
               if (j = '0') then
                  s_q  <= '0';
               else
                  s_q  <=  not s_q;
               end if;
            end if;    
        end if;
    end process p_t_ff_rst;

    -- Output ports are permanently connected to local signal
    q     <= s_q;
    q_bar <= not s_q;
end architecture behavioral;
```

### Shift register

1. Image of `top` level schematic of the 4-bit shift register. Use four D-type flip-flops and connect them properly. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

![333304118_2095885623934494_2366310159915054982_n (1)](https://user-images.githubusercontent.com/124879589/225355167-dc297381-14e6-4f82-a61f-7e464c0940a4.jpg)

