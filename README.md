# Coil Calc & Ohms Law
A command line bash script for calculating ohms law and coil winding.

## Requirements
* Bash - although this could easily be modified for a different shell
* BC
Bash is only accessible from computers running variants of Linux/BSD/MacOS X
# Coil Calc
## Usage 
### Without arguments 
Simply run './coil-calc', you will be asked to select the wire you are using from a list, the coil jig diameter, the coil lead length and the desired resistance. 

All inputs are (except selecting the wire) are provided with default values:
* Coil jig diameter: 3mm
* Coil lead lenght: 5mm
* Desired resistance: 1ohm

Each input requires a number to be entered without any alpha characters, pressing [Return] will select the default value.

### With arguments 
Coil Calc can accept the following arguments:
* -w= (or --wire=)
* -d= (or --diameter=)
* -l= (or --lead=)
* -r= (or --resistance=)

The wire argument is required, missing other arguments will result in their default value being used.

#### Examples 
To calculate the number of turns for Kanthal A1 (24AWG) using the default values for the remaingin arguemnts:
./coil-calc -w=3

To calculate the number of turns for Kanthal A1 (22AWG), with a coil jig of 2mm diameter, a lead length of 3.5mm and a resistance of 0.6ohm:
./coil-calc -w=2 -d=2 -l=3.5 -r=0.6

## Adding a custom wire
Coil calc uses a CSV file to store details of different coil wire; this method allows the end user to add their favorite wire by editing a simple text file.

What do I need to know?
* A name for your wire, this must only consist of alphabetical letters without any spaces.
* The AWG (American Wire Gauge) of the wire 
* The resistance of the wire in ohms per inch

Each data for the wire is to be sepearted by a comma; for example if the wire is 24AWG and has a resistance of 0.2 ohms per inch, the line to add would be:
* WireName,24,0.2

The details for each wire must be on their own line and the number that refers to each wire is the line number of which the wire resides in coils.csv.

# Ohms Law
## Usage 
### Without arguments 
Simply run './ohms law', you will be asked to enter the values you already know for Volts (V), Ohms (R), Watts (P) and Amps (I).

If you do not know a specific value, press [Return] to skip it.

After you have completed the requested data:

* If you have entered 2 or more values you will be presented with the data.
* If you have only entered 1 data, or the values are not integers or floats (numbers or decimal numbers) the program will exit.

### With arguments 
Ohms Law can accept the following arguments:
* -v= (or --volts=)
* -r= (or --ohms=)
* -p= (or --watts=)
* -i= (or --amps=)

In order for the calculations to work 2 arguments must be supplied, both of which must be integegers or floats (numbers or decimal numbers).

* If 2 or more valid arguments have been supplied you will be presented with the data.
* If only 1 argument is provided or the arguments are not integers or floats (numbers or decimal numbers) the program will exit.

#### Examples
To calculate for 0.4 ohms and 74 watts:
./ohms-law -r=0.4 -p=74

To calculate for 1.2 ohms at 3.2 volts:
./ohms-law -r=1.2 -v=3.2

To calculate for 4.2 amps at 52 watts:
./ohms-law -i=4.2 -p=52

# Installation (so to speak)
## Basic
Bash scripts do not as such require installing, they do on the other hand need to be marked as executable.

Open a terminal and navigate to the location of the scripts and run:
* chmod +x coil-calc
* chmod +x ohms-law

## Making it global
By default bash scripts can only be run from the directory they are located in, if you wish to make them executable from anywhere within the terminal you will need to link them to a /usr/local/bin. To do so run:
* sudo ln -s /pathtoscript/coil-calc /usr/local/bin/coil-calc 
* sudo ln -s /pathtoscript/ohms-law /usr/local/bin/ohms-law

As the coil calc script relies on a local CSV file to function you will need to modify the second line of code in coil-calc to represent the location of the script on your computer. 