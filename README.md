# MESA binary model suite for models in "Detailed evolutionary models of massive contact binaries: I. Model grids and synthetic populations for the Magellanic Clouds"
## Author: Athira Menon, email: athira.menon89@gmail.com
### **MESA version: 10398**. Feel free to edit the files/ src code for future versions. 

This is the directory of a binary model with the following initial parameters: **P= 1.0 day, q= 0.9, M1+M2= Mtotal= 26 Msun**. 
It contains the initialization files, src  and make directories. These files can be edited to evolve other close binary massive stars as well. Please follow the steps below: 

1. Prior to initializing the binary evolution, please create the necessary single star models for your binary model (here they are 12.3M_LMC.mod and 13.7M_LMC.mod). You can find the git repository for the single star models here: https://github.com/athira11/single_star_models.git. 
Copy the .mod files to your binary model directory.

2. Once you have your required .mod single star files, edit the following lines in these inlists:

   a. inlist_extra: 
  ```
  m1 = 13.7d0, m2 = 12.3d0, 
  initial_period_in_days = 1.0d0
  ```

   b.  inlist1
   ```
   saved_model_name = '13.7M_LMC.mod'
   ```
   c.  inlist2
   ```
   saved_model_name = '12.3M_LMC.mod'
   ```
 
 3. If you plan to change the metallicity of the model, please make sure the composition is correctly entered while making the single star models. In the binary inlists, you need to also edit these lines: 

   a.  inlist1
   ```
   Zbase = 0.0047d0
   ```
   b.  inlist2
   ```
   Zbase = 0.0047d0
   ```   
   
  4. Finally, cd make and edit the directory path in makefile. Compile and run the model. 
```
./clean && ./mk
./rn
```
