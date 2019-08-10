# CalculiX 2.15 for MacOS (10.14)

 [ DOWNLOAD ](https://github.com/andriitishchenko/CalculiX/releases/latest)
 
 CalculiX Version 2.15 Copyright(C) 1998-2018 Guido Dhondt
 
 based on https://github.com/bobmel/CalculiX
 
#### Using with FreeCad
https://www.freecadweb.org/wiki/Download

````
$ brew tap brewsci/science

$ brew install gmsh

$ brew install calculix-ccx  <= this will fail, so download binary by link and add symlink to $PATH

$ ln -s ~/bin/ccx_2.15 /usr/local/bin/ccx
````

#### Test 

````
$ ccx beamp

************************************************************

CalculiX Version 2.15, Copyright(C) 1998-2018 Guido Dhondt
CalculiX comes with ABSOLUTELY NO WARRANTY. This is free
software, and you are welcome to redistribute it under
certain conditions, see gpl.htm

************************************************************

You are using an executable made on Sat Aug 10 02:45:06 EEST 2019

  The numbers below are estimated upper bounds

  number of:

   nodes:          261
   elements:           32
   one-dimensional elements:            0
   two-dimensional elements:            0
   integration points per element:            8
   degrees of freedom per node:            3
   layers per element:            1

   distributed facial loads:            0
   distributed volumetric loads:            0
   concentrated loads:            9
   single point constraints:           63
   multiple point constraints:            1
   terms in all multiple point constraints:            1
   tie constraints:            0
   dependent nodes tied by cyclic constraints:            0
   dependent nodes in pre-tension constraints:            0

   sets:            6
   terms in all sets:          105

   materials:            1
   constants per material and temperature:            2
   temperature points per material:            1
   plastic data points per material:            0

   orientations:            0
   amplitudes:            4
   data points in all amplitudes:            4
   print requests:            4
   transformations:            0
   property cards:            0


 STEP            1

 Static analysis was selected

 Decascading the MPC's

 Determining the structure of the matrix:
 number of equations
 720
 number of nonzero lower triangular matrix elements
 37458

 Using up to 1 cpu(s) for the stress calculation.

 Using up to 1 cpu(s) for the symmetric stiffness/mass contributions.

 Factoring the system of equations using the symmetric spooles solver
 Using up to 1 cpu(s) for spooles.

 Using up to 1 cpu(s) for the stress calculation.


 Job finished

````

#### Compile

$ brew install gcc@8 

Clone https://github.com/bobmel/CalculiX to ~/Development/calculix/   ,it need to be done for build

````
# single thread
$ cd SPOOLES.2.2 => make lib
# multi thread
$ cd SPOOLES.2.2/MT/src => make makeLib   
# build arpack
$ cd ARPACK  => make lib
# build ccx_2.15
$ cd CalculiX/ccx_2.15/src  => make 
$ ./ccx_2.15 -v
````

