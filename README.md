AES in Cryptol
==============

Installing Cryptol
------------------

To run the Cryptol source code, you need to first install Cryptol.
There are two steps.

1. Install Cryptol
2. Install Z3

If you are on a recent version of Ubuntu, run:
   sudo apt-get install cryptol

If you cannot install Cryptol using the above command, or if you are
on a different platform. Go to http://www.cryptol.net/downloads.html
on obtain the binaries.

To run Cryptol, simply run the cryptol file in the bin folder of binary files.
Or directly enter "cryptol" in your command prompt if the binary is on
the path.

Cryptol's formal verification utilities depend on the Z3 solver by default.
Run "sudo apt-get install z3" to get Z3 on Ubuntu.
Otherwise get it from https://github.com/Z3Prover/z3/releases.

Running the Program
-------------------

In the current version of Cryptol you can only run the source code in the
interactive mode.

Run the following command to load the source code.
    cryptol AESCorrect.cry

Alternative you can run ":l AESCorrect.cry" in cryptol to load the module.

There are two source files:
- AES.cry: the implementation of AES
- AESCorrect.cry: the correctness property for the implementation

Only loading AESCorrect.cry is enough as it imports the implementation.

Once the modules are loaded, you can run the functions. For example:
     encrypt (0x3243f6a8885a308d313198a2e0370734, 0x2b7e151628aed2a6abf7158809cf4f3c)

This is an example from the AES standard document.

To prove properties, try:
   :prove shiftRowsCorrect

Similarly you can do automated tests on the property:
   :check shiftRowsCorrect

As mentioned in the report, some properties can not be proved in a feasiable
amount of time.

Please note that this program is developed and tested using Cryptol 2.2.6
on Ubuntu 16.04 (obtained through apt-get). It is possible that the program
would not function on other platforms. If you run into any trouble running it
please contact me at z72lin@uwaterloo.ca.




