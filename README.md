# vsd_lab
# Day 1 #

# Open the working Directory #

![day_1_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/b484210a-ccb8-42d3-91a8-1a5adae8b1fa)

 
  
 ##
   ls 
   
   cd Desktop
   
   cd work/tools
   
   cd openlane_working_dir
  
   cd openlane 
##
# To open the Openlane #
![day_1_2](https://github.com/shashisahu1038/vsd_lab/assets/165407652/539b5a0f-9500-4ce4-8410-65da671326d5)


  After getting into the directory, enter given below commands


#
  ls -ltr 
  
  docker
  
  pwd
  
  ls -ltr
#
**To open the openlane in interactive mode, use command-**
![day_1_3](https://github.com/shashisahu1038/vsd_lab/assets/165407652/9d61bae3-7c47-4003-a4b0-13238d4b0437)


 ./flow.tcl -interactive

#
**To prepare the openlane, use command-**

  package require openlane 0.9
  
  prep - design picorv32a
#
 # For Synthesis  
![day_1_4](https://github.com/shashisahu1038/vsd_lab/assets/165407652/e6c28df5-4047-4c2e-ae76-1a9e49120cbc)
**To run the Synthesis-**
  
  run_synthesis
#  
**-> After Synthesis is completed,we have seen all the details about the synthesis of the design(picorv32a)**

**•The Chip Area of the module 147712.918400 as shown in figure-**

![day_1_5](https://github.com/shashisahu1038/vsd_lab/assets/165407652/4d7c0656-325d-4a40-a850-f97c1e69faa6)


**•Number of cells: 14876**

![day_1_6](https://github.com/shashisahu1038/vsd_lab/assets/165407652/3c957849-b469-4a48-abd8-5aa9e935c8cf)

**•Number of FF: 1613**

![day_1_7](https://github.com/shashisahu1038/vsd_lab/assets/165407652/fb989a03-5594-4dc7-9ad7-92f3cdef9e1d)

**for the Flop ratio; We can be calculated by using the formula:**

         Flop ratio in (%) = Total No of D-FF
                           --------------------  X 100
                            Total No of Cells

                          = 1613
                          --------   X 100
                            14876 

                          = 10.8429685

# Synthesis Report-:
#
**We can find Synthesis Report in the directory**

     /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/30-03_04-14/reports/synthesis/1-yosys_4.stat.rpt

**We can find Synthesis Report in the directory**

     /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/30-03_04-14/results/synthesis/picorv32a.synthesis.v







