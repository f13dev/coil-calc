# coil-calc
A command line bash script for calculating ohms law and coil winding.

# Requirements
* Bash - although this could easily be modified for a different shell
* BC

# Usage 
## Without arguments 
Simply run './ohms law', you will be asked to enter the values you already know for Volts (V), Ohms (R), Watts (P) and Amps (I).

If you do not know a specific value, press [Return] to skip it.

After you have completed the requested data:
*If you have entered 2 or more values you will be presented with the data.
*If you have only entered 1 data, or the values are not integers or floats (numbers or decimal numbers) the program will exit.

## With arguments 
Ohms Law can accept the following arguments:
* -v= (or --volts=)
* -r= (or --ohms=)
* -p= (or --watts=)
* -i= (or --amps=)

In order for the calculations to work 2 arguments must be supplied, both of which must be integegers or floats (numbers or decimal numbers).

*If 2 or more valid arguments have been supplied you will be presented with the data.
*If only 1 argument is provided or the arguments are not integers or floats (numbers or decimal numbers) the program will exit.

### Examples
To calculate for 0.4 ohms and 74 watts:
./ohms-law -r=0.4 -p=74

To calculate for 1.2 ohms at 3.2 volts:
./ohms-law -r=1.2 -v=3.2

To calculate for 4.2 amps at 52 watts:
./ohms-law -i=4.2 -p=52