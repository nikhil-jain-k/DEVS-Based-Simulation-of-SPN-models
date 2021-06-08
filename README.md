
# Information
The Stochastic Petri Net Package (SPNP) is an adaptable and versatile modelling tool 
for the solution of Stochastic Reward Nets. The package has been used by many 
different research facilities and organizations around the world to study and model 
complex concurrent processes in a real distributed system. However, this popular 
package can only generate an analytic-numeric solution for the SRN models 
implemented in it, which causes a problem when the state space of the system 
becomes too large; in which case, only simulation modelling methods are useful. This 
thesis project provides a solution to this problem by adding discrete-event simulation 
capabilities to the SRN models implemented in the SPNP package. The simulation 
methodology is useful in particular, for non-Markovian SRNs. Discrete Event System 
Specification (DEVS) is the simulation formalism used to reach at this solution. This Github 
project provides an approach to integrate two systems namely: the SPNP package and 
the DEVS engine, with discrete-event simulation capabilities. The solution is achieved 
via the use of a parser that establishes a stable communication between these two 
systems and initiates simulation for the input SRN models from the SPNP package in 
the DEVS engine.

# Installation instructions

## Prerequisites
1. Latest MS Visual Studio
2. Windows OS

## Installing the SPNP Package
1. Extract the Spnp-Gui.zip and DEVS-Engine.zip in C:\.
2. Search for Environmental Variables Dialog in Control Panel.
3. In the Environment Variables Menu, under “User Variables”, edit “Path”
variable and add "C:\Spnp-Gui\spnp\bin" (use ';' before adding on a 
populated path variable).
4. In the Environment Variables Menu, under “System Variables”, add a new 
variable by the name “SPNP_DIRECTORY” and its value as “C:\Spnp-Gui\spnp” respectively.
5. If using administrator and user account together, then in the Environment 
Variables Menu, under “System Variables”, edit “Path” and add “C:\Spnp-Gui\spnp\bin” (use ';' before adding on a populated path variable).

## Adding the Parser tool and the Reset DEVS Engine to PATH
1. Extract the parser.zip to C:\.
2. <path-to-the-parser-folder> to “Path” under System variables in the 
Environment Variables Menu.
3. Edit RESETDEVS.bat file and <path-to-the-parser-folder> and the <path-to-the-SPNP2DEVS-folder-in-DEVS-Engine> at the specified place.

# Execution Instructions
## Executing the SPNP Package
1. Execute “gui” in the “C:\Spnp-Gui” directory to open the SPNP package.
2. Import/create a model in the GUI by clicking File->New (Give project name and
model name) or File->Open Project.
3. Click on Analysis Editor->Analysis, and select from the output lists (“Expected 
reward rate in steady-state”) in Analysis Frame then click “Add”.
4. Click Run, and the CSPL file (.c) file along with the log and the output file 
would be stored in the “C:\Spnp-Gui\” directory.
The analytic-numeric solution could be viewed in the “.out” file. 

## Executing the Parser Tool and the DEVS Engine
1. Open cmd prompt, type the command:
parser.exe <path_to_cspl_file> <path_to_spnp2devs_folder>
2. Open SPNP2DEVS.sln file, build and execute solution file.
3. In the DEVS GUI, click on Simulation->Generate MakeSES
4. Build and execute the solution file.
5. In the DEVS GUI, click on Simulation->Start Simulation.
6. Input custom parameters in the “Properties” or leave as is and click on “Run 
Simulation”

A viewable discrete event simulation output would be generated on the DEVS-Engine GUI. This simulation output could be saved to a file.
(Run “RESETDEVS” from cmd prompt to reset the DEVS-Engine and repeat the simulation process.)
