# vsd_lab
# Day 1 

### Open the working Directory for using openlane 

![day_1_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/b484210a-ccb8-42d3-91a8-1a5adae8b1fa)
  
     ls 
     cd Desktop
     cd work/tools
     cd openlane_working_dir
     cd openlane 
##
### To open the Openlane we do
![day_1_2](https://github.com/shashisahu1038/vsd_lab/assets/165407652/539b5a0f-9500-4ce4-8410-65da671326d5)


  **After getting into the directory, enter given below commands**


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
 ## For Synthesis  
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

## Synthesis Report-:
#
**We can find Synthesis Report in the directory**

     /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/30-03_04-14/reports/synthesis/1-yosys_4.stat.rpt

**We can find Synthesis Report in the directory**

     /home/vsduser/Desktop/work/tools/openlane_workging_dir/openlane/designs/picorv32a/runs/30-03_04-14/results/synthesis/picorv32a.synthesis.v





#
# Day 2 

## Floorplanning 

**The LAB for day 2 gives the complete flow of the Floorplanning and the placement process**
![D_2_P_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/7ff59b13-9962-4469-abfe-2cd06e37c445)

**The configuational file present in this location**

     /home/vsduser/Desktop/work/tools/openlane_workging_dir/openlane/configurations/README.md

#
To run floorplan

  run_floorplan
we will be getting a success message like this

![floorplan_RUN_succesfully](https://github.com/shashisahu1038/vsd_lab/assets/165407652/1d2888f1-fb8e-41cc-af71-8e206e79c86c)

In this particular location from the floorplan.def file, we can able to see the area of the chip

![Day2_def](https://github.com/shashisahu1038/vsd_lab/assets/165407652/c7c50f5c-4253-4f3f-b7c2-3da221593112)
 

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
**Open this directory to launch the Magic Tool**
![day_2_open_magic](https://github.com/shashisahu1038/vsd_lab/assets/165407652/c4f2c120-f46a-43cd-98e5-22664b90771e)

**Locate to this directory**

    ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/29-03_15-37/results/floorplan

    magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
#
**layout of Design in Floorplan stage inside Magic**

![d_2_def_clear](https://github.com/shashisahu1038/vsd_lab/assets/165407652/408c7a7d-10ee-4f43-b1e4-2353658e71e1)

#
**Horizontal metal layer description**
![day_2_horizontal_layer](https://github.com/shashisahu1038/vsd_lab/assets/165407652/bcf9ccf4-3714-409c-a18a-52defe9a0796)

#
**Vertical metal layer description**

![d_2_vertical_layer](https://github.com/shashisahu1038/vsd_lab/assets/165407652/9ddcdc86-c316-4398-b6fa-7702876634da)

#
**Standard cells layout in floorpan stage**

![d_2_std_cells](https://github.com/shashisahu1038/vsd_lab/assets/165407652/3f0cee0c-d117-4303-b75d-6467f6f01f19)


#

# Placement
To run the Placement, the command is

     run_placement
#
**we will be getting a success message like this**
![d_2_run_placement](https://github.com/shashisahu1038/vsd_lab/assets/165407652/24449dbc-6e85-4a48-85da-2a12c65d0b20)

# 
**Commands to load placement def in magic**

     magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
![D-2_directory of placement](https://github.com/shashisahu1038/vsd_lab/assets/165407652/0a3af577-19db-4e03-9fde-0a223500337a)

 #   
**layout of designin placement inside magic**
![D-2_def_placement ](https://github.com/shashisahu1038/vsd_lab/assets/165407652/712f9b42-423e-429b-8bc7-3339335038d3)

**Standard cell layout in placement stage**
![stdcell_placenment_stage](https://github.com/shashisahu1038/vsd_lab/assets/165407652/1727f075-6791-40e0-aa80-2f8d9ce9209f)


# DAY-3

**The LAB for the day gives the complete flow of the Inverter simulation using ngspice and Magic EDA tool**

we need to put our custom inverter into design; for this purpose, we need to custom inverter file which is present on github. 

**So we need to go on openlane directory & cloning this file here**. 

            /Desktop/work/tools/openlane_working_dir/openlane
#
**we clone the files from github to here by given below command**
             
              git clone https://github.com/nickson-jose/vsdstdcelldesign.git  
![D_3_gitclone](https://github.com/shashisahu1038/vsd_lab/assets/165407652/9eec39f2-1a71-4bd5-91d6-9bb72de37a6e)

We need to open Mac file for viewing diffrent layer which building inverter. Before opening mac file we need to have magic tech file.So we need to copy these files on our location.

**magic Tech file location** 

         /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic

copy the sky130A.tech file from this location to the our location (custom inverter files location)
![d_3_3_copytechfile](https://github.com/shashisahu1038/vsd_lab/assets/165407652/b522d764-3e99-4cd1-adca-fceba614a8ec)

Now initialize magic

         magic -T sky130A.tech sky130_inv.mag &
![d-3_4_initializing_magic](https://github.com/shashisahu1038/vsd_lab/assets/165407652/ddda4939-b5d9-4ecf-aac0-4d5a90ab0907)

* Inverter layout
![d_3_5_inverter_layout](https://github.com/shashisahu1038/vsd_lab/assets/165407652/d754e36f-984b-4dc9-acc5-a883c740f062)

* **Nmos layout**

When polydiffusion crosses N-diffusion known as Nmos.So selection of nmos we  type "s" & open tkcon.tcl, type what to know it is Nmoss or Pmos
  ![d_3_6_nmos_layout](https://github.com/shashisahu1038/vsd_lab/assets/165407652/53422920-8990-4db1-8d4c-1786876922d2)

* **Pmos layout**

When polydiffusion crosses P-diffusion known as Pmos. So selection of nmos we  type "s" & open tkcon.tcl, type what to know it is Nmoss or Pmos.
  ![d_3_7_pmos_layout](https://github.com/shashisahu1038/vsd_lab/assets/165407652/a34489d4-246e-4a91-b211-46ee4f449bad)
  
* **Connection between source of Nmos and drain of Pmos(checking output connection)**
  ![d_3_8_source_drain_layout](https://github.com/shashisahu1038/vsd_lab/assets/165407652/e8dc40fd-0910-4bfb-9e70-ba51ac5843d7)

* **Connection between source and VDD in Pmos**

For seeing connection we put cursor on "Pmos" & type two times "s". we see that Pmos connected to Vdd.
![d_3_9_pmos_vdd_layout](https://github.com/shashisahu1038/vsd_lab/assets/165407652/dca529e2-4a25-41ec-8ea7-ea2219ec83b3)

* **Connection between source and gnd in Nmos**
For seeing connection we put cursor on "Nmos" & type two times "s". we see that Nmos connected to gnd.
![d_3_10__nmos_gnd_layout](https://github.com/shashisahu1038/vsd_lab/assets/165407652/8ad2e207-2d44-4a33-851e-100dd3315bd4)

# 
For knowing logical functioning of Inverter,we would 1st extract spice then we would to spice silution on ngspice simulator.
**So we open the tkcon window and type given below the commands for extracting the files**
![d_3_11_spice_extration](https://github.com/shashisahu1038/vsd_lab/assets/165407652/2e748b0f-6038-4fed-ba24-5d1c7088a394)

     pwd
     extract all
After extraction it gives a file name as "sky130_inv.ext" on our location
![d_3_12_extraction_file_location](https://github.com/shashisahu1038/vsd_lab/assets/165407652/81270a04-b06e-4b4e-8fc2-b689f22f6802)

we use 'sky130_inv.ex' file generation of spice file which we are using in ngspice

**generating spice file for ngspice by using these commands**  
    
     ext2spice cthresh 0 rthresh 0
     ext2spice  

By using these commands we extract all paracitic capacitance.
![d_3_13_spice_generate_file](https://github.com/shashisahu1038/vsd_lab/assets/165407652/692d4508-b939-4937-a7eb-bbefa37ab3fe)

#
## Spice Simulation
Now in the git cloned location, we can able to see the sky130_inv.spice file

**To install ngspice, use the commands in the terminal**
    
     sudo apt -y install ngspice
Then run the spice file in ngspice

     ngspice sky130_inv.spice

#
#
* **Spice Output**
#
#
**To plot the graph between Voltage and time type the command in ngspice**
     
     plot y vs time a
























