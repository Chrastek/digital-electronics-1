# Lab 6 Jakub Chrastek

### Bidirectional counter

1. Listing of VHDL code of the completed process `p_cnt_up_down`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines

```vhdl
    --------------------------------------------------------
    -- p_cnt_up_down
    -- Clocked process with synchronous reset which implements
    -- n-bit updown counter.
    --------------------------------------------------------
    p_cnt_up_down : process (clk) is
  begin

    if rising_edge(clk) then
      if (rst = '1') then           -- Synchronous reset
        sig_cnt <= (others => '0'); -- Clear all bits
      elsif (en = '1') then         -- Test if counter is enabled
        if (cnt_up = '1') then
            sig_cnt <= sig_cnt + 1;
        elsif (cnt_up = '0') then
            sig_cnt <= sig_cnt - 1;   
        end if;     
      end if;
    end if;

  end process p_cnt_up_down;
```

2. Screenshot with simulated time waveforms. Test (a) reset, (b) counter direction, (c) enable. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![image](https://user-images.githubusercontent.com/124675666/226162570-3f04aa91-1107-4b0c-a129-9f2bbcbeab34.png)

### Two counters

1. Image of the top layer structure including both counters, ie a 4-bit bidirectional counter from Part 4 and a 12-bit counter with a 10 ms time base from Experiments on your own. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

   ![226164837-293a0df4-fbb5-42ed-9230-9b751c311570](https://user-images.githubusercontent.com/124879589/226964679-4295ffcd-a359-479e-8806-4e84c8a6e4e3.png)


