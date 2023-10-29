# RaspberryPi-EtherCAT-Slave

Step 1: Install MSCL Package
Follow the instructions for installing the MSCL package from the official repository: https://github.com/LORD-MicroStrain/MSCL


Step 2: Compile the C++ Program

First, set the LD_LIBRARY_PATH to include the MSCL library:
export LD_LIBRARY_PATH=/usr/share/c++-mscl:$LD_LIBRARY_PATH

Update the dynamic linker's cache to include the MSCL library:
sudo ldconfig /usr/share/c++-mscl

Set the LD_LIBRARY_PATH to include the MSCL library for the current session:
sudo LD_LIBRARY_PATH=/usr/share/c++-mscl

Compile your C++ file (e.g., YourFile.cpp) using g++ with the necessary flags:
g++ -I/usr/share/c++-mscl/source -I/usr/share/c++-mscl/Boost/include YourFile.cpp -o YourProgram -L/usr/share/c++-mscl -lmscl -lstdc++ -std=c++11 -lpthread


Step 3: Run the Executable

Execute the compiled program by running:
sudo ./Stream_IMU_Data
