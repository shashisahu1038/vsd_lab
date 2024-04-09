# VSD Workshop -

#**SoC_Design_and_Chip_Planning_Using_OpenLane**
#
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
Introduction to timing libs and steps to include new cell in synthesis
**•The Chip Area of the module 147712.918400 as shown in figure-**
steps to convert magic layout to std cell LEF
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
    
**open Magic for viewing layout**
    
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
for spice simulation in ngspice, we need spice file which is generated by previous step. We can able to see this file name as "sky130_inv.spice" is our prsent location.Before running file in ngspice, we should follow some steps to create final SPICE deck using Sky130 tech.Inside sky130tech file, we can see the all details about the connectivity of the NMOS, PMOS and the power supply(Vdd & gnd) .
X0 is NMOS and X1 is PMOS and both's connectivity is shown as GATE DRAIN SUBSTATE SOURCE.

**Let's check "sky130_inv.spice" file contains**
![d_3_14_spice130A](https://github.com/shashisahu1038/vsd_lab/assets/165407652/f1186a11-ad8b-4a6d-89e5-03d202f508b4)

**Here we can see our final dec**
For Now we have to include the PMOS and NMOS lib files. it is inside the libs folder which is present under vsdstdcellsdesign folder.We are giving these files because we want to control inputs also.

So we edit "sky130_inv.spice" file.We set the supply voltage "VDD" to 3.3v by VDD VPWR 0 3.3V command. Similarly we set the value of "VSS" to to 0v by VSS VGND 0 0V command. 

Now, we need to specify the input files. by Va A VGND PULSE(0V 3.3V 0 0.1ns 0.1ns 2ns 4ns).

Also add the command for the analysis like, .tran 1n 20n, .control , run,.endc,.end.

we also change pshort to pshort_model.0 & nshort to nshort_model.0. Now our file deck ready for simulation.
![d_3_15_spice130A_modified](https://github.com/shashisahu1038/vsd_lab/assets/165407652/c133d375-0fd2-4428-bb2b-9120d1b7b2a9)

**To install ngspice, use the commands in the terminal**
    
     sudo apt -y install ngspice
**Then run the spice file in ngspice**

     ngspice sky130_inv.spice
     
**After running this file we get output of ngspice like this**

![d_3_16_ngspice_simulation](https://github.com/shashisahu1038/vsd_lab/assets/165407652/cc35a30e-837e-42e9-8c6b-cf46c002e358)

**To plot the graph between Voltage and time type the command in ngspice**
     
     plot y vs time a
![d_3_17_plot_yvstime](https://github.com/shashisahu1038/vsd_lab/assets/165407652/9dc8eac7-07af-4b0e-9505-c5f67cf54a08)

if we increase the C3 value from 0.024ff to 2ff the graph will look like this, graph become more smoother.
![d_3_17_plot_yvstime_modified](https://github.com/shashisahu1038/vsd_lab/assets/165407652/1056f3cb-408e-4522-b7d8-147897c354de)


## Steps to characterize inverter using sky130 model files
* **Here, we have to find value of 4 parameters**

* **rise time**
it is time taken to the output waveform to 20% value to 80% value.

![d_3_19_plot_rise_calculation](https://github.com/shashisahu1038/vsd_lab/assets/165407652/21c00c55-75a7-49b6-8541-f9b7602f4e42)

* 80% value of rising rising output
  ![d_3_18_plot_rise time_80](https://github.com/shashisahu1038/vsd_lab/assets/165407652/a492221e-e2bc-4f60-8694-5bcd563e393b)
  
* 20% value of output
  ![d_3_18_plot_rise_20](https://github.com/shashisahu1038/vsd_lab/assets/165407652/b016a29e-47c0-4c89-ad85-e0e63e938135)


so, rise time= (2.24688 - 2.18214)e-09 = 64.74 psec.

* **fall time**
it is the time take by output for transition from 80% to 20%.

![d_3_17_plot_fall_calculation](https://github.com/shashisahu1038/vsd_lab/assets/165407652/0504d554-4100-4bef-add8-f6753f8de6d3)


* 80% value of falling output
![d_3_17_plot_fall_80](https://github.com/shashisahu1038/vsd_lab/assets/165407652/54668daa-6cd5-4499-80d5-db95a9632499)

* 20% value of falling output
![d_3_17_plot_fall_20](https://github.com/shashisahu1038/vsd_lab/assets/165407652/37f976af-7bed-4f91-9485-1bae873d85a0)

  
so, rise time= (4.09397 - 4.05089e-09 = 43.08 psec.

* 
* **cell rise delay**
it is the time difference between output falling to 50% and input is rising to 50%.
* 50% of rising ouput & 50 % of falling input
![d_3_19_plot_cell_rise_delay](https://github.com/shashisahu1038/vsd_lab/assets/165407652/41aeadad-df31-474f-b8ab-1b74405113ab)


  ![d_3_19_plot_cell_rise_delay_calculation](https://github.com/shashisahu1038/vsd_lab/assets/165407652/f9007b8b-8941-4647-b906-d93f7aef5893)

so, propogation delay =(6.21119 - 6.15)e-09 = 61.19 psec.

* **cell fall delay**
it is time difference between output falling to 50% and input is rising to 50%.
* 50% of rising ouput & 50 % of falling input
![d_3_19_plot_cell_fall_delay](https://github.com/shashisahu1038/vsd_lab/assets/165407652/b0ef6e57-7b9b-44bd-bf43-a7d7aa29adca)

  
    ![d_3_19_plot_cell_fall_delay_calculation](https://github.com/shashisahu1038/vsd_lab/assets/165407652/9f7dd87e-a221-45de-be10-f0047463acfb)

so, cell fall delay =(4.07588 - 4.05022)e-09 = 25.66 psec.

We have successfully characterized our inverter. Our next objective is to create a lef file using the layout and we will plugin this lef file in the picorv32a core
#
## DRC rules & DRC check in Magic-

**To know more about the Magic DRC; visit the website:-**

      http://opencircuitdesign.com/magic/Technologyfiles/TheMagicTechnologyFileManual/DrcSection

Link to Google_Skywaters Design Rules: - 

      https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html

For reference , we can use the github repo of Google-Skywater: -

      https://github.com/google/skywater-pdk

 #

 ## DRC rule check in Magic-

We need to download some pdk for design so that we apply DRC on design.
 
**follow steps for DRC rule check-**

Step-1  Download the lab files for performing DRC corrections by link-

     wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
     
Step-2 extract the lab files from the downloaded file by command

    tar xfz drc_tests.tgz

Step-3 go inside extracted directory(drc_tests)

    cd drc_tests

Step-4 open magic by command

     magic -d XR

Step-4 Open any file for DRC checking(for example- met3.mag) check DRC by selecting a layout by command in tkcon

     drc why

![D_3_DRC_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/021f8d6d-0093-46d7-ada8-e0fd20fb9e39)

![D_3_DRC_2](https://github.com/shashisahu1038/vsd_lab/assets/165407652/843912ac-0dda-4316-b5c8-c9d7f2ca7b07)

![D_3_DRC_3](https://github.com/shashisahu1038/vsd_lab/assets/165407652/fa12593b-3f5a-43b8-8290-f8774053a437)

![D_3_DRC_4](https://github.com/shashisahu1038/vsd_lab/assets/165407652/7bdb5dab-de5d-4879-bd48-2a927509014c)

![D_3_DRC_5](https://github.com/shashisahu1038/vsd_lab/assets/165407652/16b6ff3f-8d72-4407-afab-d90a7bb17eb6)

![D_3_DRC_7](https://github.com/shashisahu1038/vsd_lab/assets/165407652/e1a4a848-1431-4351-8a30-c2bbc3d05835)

![D_3_DRC_8](https://github.com/shashisahu1038/vsd_lab/assets/165407652/68cf713b-8ca0-4cf3-948d-68da84499856)

![D_3_DRC_9](https://github.com/shashisahu1038/vsd_lab/assets/165407652/0922de4a-cb48-4852-95be-ebca58e90dbb)

![D_3_DRC_10](https://github.com/shashisahu1038/vsd_lab/assets/165407652/a2c95b03-9761-4cc2-b8ee-0f840514dba6)


# Day 4 - Pre-layout timing analysis and importance of good clock tree

## **Timing modeling using delay tables**

### **steps to convert grid info to track info**

**S-1 open magic & press "g" for grid in layout**

**S-2 open track.info file & use that data for convert grid into track by using tkcon. You can see figures.**
![D_4_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/5d06eb74-fc7c-46bd-997c-fbeb422a9a81)

![D_4_2](https://github.com/shashisahu1038/vsd_lab/assets/165407652/76711408-0345-48cb-8fd1-3c5eadc2fffc)

![D_4_3](https://github.com/shashisahu1038/vsd_lab/assets/165407652/7bdc19c8-a3e0-4878-bdf6-2bd1b4e75b81)

### **steps to convert magic layout to std cell LEF**

![D_4_4](https://github.com/shashisahu1038/vsd_lab/assets/165407652/7bb54393-36f3-49e5-93a0-5b4fb8b03c2b)

![D_4_5](https://github.com/shashisahu1038/vsd_lab/assets/165407652/3fbcdace-1bc7-49f7-b7a0-869db02f06ca)

![D_4_6](https://github.com/shashisahu1038/vsd_lab/assets/165407652/99630380-9eed-4190-bf57-3e4b53245768)

![D_4_7](https://github.com/shashisahu1038/vsd_lab/assets/165407652/bd6cc0fa-b174-4555-9efb-d90b774feb63)

![D_4_8](https://github.com/shashisahu1038/vsd_lab/assets/165407652/5b93abd9-4d26-43a9-b2ef-a6f1fb49db35)

![D_4_9](https://github.com/shashisahu1038/vsd_lab/assets/165407652/8e07738a-243d-4f43-8296-9cfdce6cac94)

![D_4_10](https://github.com/shashisahu1038/vsd_lab/assets/165407652/1bce3159-12ca-49c6-9e26-c6279f8158de)


### **Introduction to timing libs and steps to include new cell in synthesis**

![lab_3_1](https://github.com/shashisahu1038/vsd_lab/assets/165407652/c5559997-d024-4d83-8802-a444fc53a082)

![lab_3_2](https://github.com/shashisahu1038/vsd_lab/assets/165407652/8e6f011c-5302-4e6a-ab1d-ff3737c64967)

![lab_3_3](https://github.com/shashisahu1038/vsd_lab/assets/165407652/4ae64728-84e0-464b-81fc-55e58f0a9cce)
 
**now we will try to use this custom standard cell in out picorv32a design so for that we will be copying all the library files and lef file and adding the required changes in the config.tcl file.
Command forn that-**

       set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
       set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
       set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
       set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

       set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]






















