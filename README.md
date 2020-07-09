# IP DESIGN REPORTING 
# DATA SHEET
## vsdbbcud4f
Bi-directional Buffer with Non-inverting CMOS input and gated Pull-down and Pull-up, Strength 4ma @ 3.3V, Normal, High noise
## DESCRIPTION OF IP
1) vsdbbcud4f is a GPIO pin (General purpose input/output)
2) The GPIO pin is controlled by the user to get a desired mode of the whole chip
3) The input/output mode can be selected by giving the enable pin to logic high or low
4) Both the buffers are connected in a bidirectional fashion which allows the data to flow in either of the direction
## SYMBOL
![image](https://user-images.githubusercontent.com/66250226/86907415-9c1ea100-c132-11ea-8f2f-0c5a9970baf4.png)
## Block diagram
![image](https://user-images.githubusercontent.com/66250226/85789018-80d38f00-b74b-11ea-9124-9c9f1f7b236f.png)

## PIN DESCRIPTIONS
1) pin A is where the input is given
2) pin EN is the enable pin which is used to determine the mode of the circuit (input/output)
3) pin PI is the input to the PAD cell
4) pin PUEN is used to pull-up the input when it is in floating state
5) pin PDEN is used to pull-down the input when it is floating state
6) pin Y is the output
7) pin PO is the output of the PAD cell
## TYPICAL PERFORMANCE CHARACTERISTICS
## specifications of the IP
 ![image](https://user-images.githubusercontent.com/66250226/85953985-de591d00-b991-11ea-9d62-3d8c232a24f3.png)
 
## pre-layout characterstics 
## LT-Spice circuit diagram
![image](https://user-images.githubusercontent.com/66250226/85953888-46f3ca00-b991-11ea-92dd-3346e886a278.png)

## LTspice output graph for a simulation time of 100ms
![image](https://user-images.githubusercontent.com/66250226/87010568-5b7f6000-c1e4-11ea-9a0e-bc08eb88029d.png)

## ngspice plots
![image](https://user-images.githubusercontent.com/66250226/87011129-23c4e800-c1e5-11ea-95fa-786a7f261c8d.png)

## post-layout characterstics
### cmos magic layout
![image](https://user-images.githubusercontent.com/66250226/87004407-fa06c380-c1da-11ea-8475-0d9a1c4a84ed.png)
### ngspice plots for cmos layout

```ngspice cmos.sp```

![image](https://user-images.githubusercontent.com/66250226/87004613-536ef280-c1db-11ea-8d5d-714cb6dbfd04.png)
### nand gate magic layout
![image](https://user-images.githubusercontent.com/66250226/87004724-87e2ae80-c1db-11ea-9e7b-f6c49fc1bd07.png)
### ngspice plots for nand layout

```ngspice nand.sp```

![image](https://user-images.githubusercontent.com/66250226/87004974-ead44580-c1db-11ea-93b5-777616588d46.png)

### tristate magic layout
![image](https://user-images.githubusercontent.com/66250226/87005198-46063800-c1dc-11ea-9007-71fe5739026d.png)

### ngspice plots for tristate layout

```ngspice tristate.sp```

![image](https://user-images.githubusercontent.com/66250226/87006607-97172b80-c1de-11ea-9d03-febcff53ddda.png)

### gpio magic layout
![image](https://user-images.githubusercontent.com/66250226/87006818-ea897980-c1de-11ea-82a2-05d20b557f97.png)

### ngspice plots for gpio layout

```ngspice gpio.sp```

![image](https://user-images.githubusercontent.com/66250226/87007292-a34fb880-c1df-11ea-837e-4352b068dcce.png)


## FUTURE WORK
ISSUES:
1) performance of the pre-layout simulation is limited to milliseconds simulation time should update it to get all the plots in nanoseconds since we are using everything in 180nm technology
2) PUEN and PDEN are not included in post layout simulation yet
##### these issues are to be updated in further releases 

# IP USAGE

## TOOLS REQUIRED TO USE THE IP

# For pre-layout simulation
## steps to install and use ltspice for windows10
1) Download LTspice from here [ltspice_download](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html#)
2) Now click on the download button for windows.
3) Now click on the application `ltspice` from your downloads and accept and continue. 
4) The simulator is installed and is ready to use.
5) download the ```ltspice``` zip file from the repository
6) open the circuit with a file .asc file extension
7) goto ```view->spice netlsit``` and copy the content in there
8) open a new text file and paste the spice netlsit and add the command lines according to ngspice
9) save the text file with a .cir extension

## Ngspice installation and usage for windows 10
ngspice is the open source simulator.
Follow the steps below to install ngspice on windows10:
1) Click on [this](http://ngspice.sourceforge.net/download.html) to download ngspice software. 
2) Click on the download button.
3) You are directed to the download page. Then follow the installation steps.
4) The software is now donloaded and ready to use.
5) open ```ngspice->spice64->bin``` and save the .cir file in this location also add the model files in the same location
6) now open ngspice application and type filename.cir to get the corresponding output graphs

# For post layout simulation
## MAGIC installation and usage in linux mint
1) goto ```administartion->synaptic package manager->search->magic```
2) mark it for installation and proceed with the next steps
3) once the installation is completed close the synaptic manager
4) download the above files from repository and unzip them
5) open the terminal in the folder and tpye ```magic -T osu180nm.tech filename.mag``` for example if we want to open the gpio layout type ```magic -T osu180nm.tech gpio.mag```
6) This opens the layout
7) now goto the corresponding tckon dialoge box and type ```extract all``` which generates a netlist with the extension ext now to convert into spice type ```ext2spice```
8) a spice netlsit is generated open it and add the pmos and nmos model files and some lines to run it through ngspice
9) save the files with a .sp extension

## Ngspice installation and usage for linux mint
1) goto ```administration->synaptic package manager->search->ngspice```
2) mark it for installation and proceed with further steps
3) open in terminal->ngspice and check if it is working to come out of ngspice type ```exit``` in terminal
4) type ```ngspice filename.sp``` and check the output graphs


# Contact information:
1) Nalla Gowthami, Electronics and instrumentation engineering, NIT Rourkela, gowthaminalla1821@gmail.com
2) Kunal Gosh Director, Vsd Corp Pvt.Ltd, kunalpgosh@gmail.com
3) Phillip Guhring, Software architect at Libresilicon Association pg@futureware.at
4) Dr.Gaurav Trivedi Co-principal investigator, EICT academy, and associative proffessor, EEE depatement, IIT Guwahati, trivedi@iitg.ac.in

