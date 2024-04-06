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

     /home/vsduser/Desktop/work/tools/openlane_workging_dir/openlane/designs/picorv32a/runs/30-03_04-14/results/synthesis/picorv32a.synthesis.v





#
# Day 2 #

# Floorplanning #

**The LAB for day 2 gives the complete flow of the Floorplanning and the placement process**
![D_2_P_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/7ff59b13-9962-4469-abfe-2cd06e37c445)

The configuration files are inside the location

  /Desktop/work/tools/openlane_working_dir/openlane/configurations/README.md
#
To run floorplan

  run_floorplan
we will be getting a success message like this
![floorplan_RUN_succesfully](https://github.com/shashisahu1038/vsd_lab/assets/165407652/1d2888f1-fb8e-41cc-af71-8e206e79c86c)




In this particular location from the floorplan.def file, we can able to see the area of the chip
    # 
    1000 unit distance = 1 Micron

         Distance in micron = value
                            ----------
                               1000

        Die width in micron = 660685 
                             ---------
                               1000
                            
       Die height in micron =  671405 
                              ---------
                                1000

      Area of die in micron = 660.685*671.405 Square micron 

# 
Open this directory to initiate the Magic Tool
Locate to this directory

  ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/29-03_15-37/results/floorplan

magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
#
Floorplan def in Magic
#
#
Horizontal metal layer
#
#
Vertical metal layer
#
#
Standard cells
#
#

# Placement
To run the Placement, the command is
#
#
run_placement
# 
Commands to load placement def in magic
#
#
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
#
Floorplan def in magic
#
#
Standard cell placement
#
#
# DAY-3

The LAB for the day gives the complete flow of the Inverter simulation using ngspice and Magic EDA tool
#
#
































