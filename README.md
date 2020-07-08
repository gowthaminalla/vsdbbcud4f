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
## PIN DESCRIPTIONS
1) pin A is where the input is given
2) pin EN is the enable pin which is used to determine the mode of the circuit (input/output)
3) pin PO is one of the NAND gate inputs
4) pin PUEN is used to pull-up the input when it is in floating state
5) pin PDEN is used to pull-down the input when it is floating state
6) pin Y is the output
7) pin PO is the output of the NAND gate where Y and PO are the inputs.
## TYPICAL PERFORMANCE CHARACTERISTICS
## specifications of the IP
 ![image](https://user-images.githubusercontent.com/66250226/85953985-de591d00-b991-11ea-9d62-3d8c232a24f3.png)
## LT-Spice circuit diagram
![image](https://user-images.githubusercontent.com/66250226/85953888-46f3ca00-b991-11ea-92dd-3346e886a278.png)
## FUTURE WORK

# IP USAGE
## TOOLS REQUIRED TO USE THE IP
1) LTSPICE
## steps to install ltspice for windows10
1) Download LTspice from here [ltspice_download](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html#)
2) Now click on the download button for windows.
3) Now click on the application `ltspice` from your downloads and accept and continue. 
4) The simulator is installed and is ready to use.

## Installation steps for Ubuntu
Follow the steps given below to install Ltspice simulator in Ubuntu.
1) LINUX Users have to install WINE from [here](https://wiki.winehq.org/Download) as LTSpice is not directly supported.
2) Similar steps are followed as mentioned for windows to download LTspice setup.
3) Right click on the downloaded setup file from your downloads and select the option Open With Wine Windows Program Loader.
4) After this, the basic installation steps are followed.

## NGspice installation 
ngspice is the open source simulator. 

## Ngspice installation for windows 10

Follow the steps below to install ngspice on windows10:

1) Click on [this](http://ngspice.sourceforge.net/download.html) to download ngspice software. 
2) Click on the download button.
3) You are directed to the download page. Then follow the installation steps.
4) The software is now donloaded and ready to use.

## Ngspice installation for ubuntu
click on Copy button to copy the command and paste into your command line terminal using built-in APT package manager.
1) Run update command to update package repositories and get latest package information.
`sudo apt-get update -y`
2) Run the install command with -y flag to quickly install the packages and dependencies.
`sudo apt-get install -y ngspice`
3) Check the system logs to confirm that there are no related errors. 
Note: `-y` flag means to assume yes 

## STEPS TO CLONE IP


