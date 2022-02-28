# Lab 2: Daniel Smyd

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![K-maps](images/kmap_greater.png)

   Less than:

   ![K-maps](images/kmap_less.png)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function:

   ![Logic functions](images/greater_SoP.png)
   
   and simplified PoS (Product of the Sums) form of the "less than" function: 
   
   ![Logic functions](images/less_PoS.png)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **xxxx25**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
        s_b <= "0010"; -- Such as "0101" if ID = xxxx56, BCD of my second last ID digit =>(2)
        s_a <= "0101"; -- Such as "0110" if ID = xxxx56, BCD of my last ID digit =>(5)
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and -- chybná odpověd
                (s_B_equals_A  = '0') and 
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0010, 0101 FAILED" severity error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![your figure](images/console_screen.png)

3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/...](https://www.edaplayground.com/x/w4CL)
