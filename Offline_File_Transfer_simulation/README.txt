README.txt

This folder contains the OFFLINE FILE TRANSFER DEVS model implemented in Cadmium

/**************************/
/****FILES ORGANIZATION****/
/**************************/

README.txt	
OfflineFileTransferSimulation.doc
LogFiles [This folder contains logs of all the test cases run on the atomic models]
OFT.xml  [This file contains the specifications and descriptions of the atomic/coupled model]
DEVSModelForm

makefile

atomics [This folder contains atomic models implemented in Cadmium]
	FileServerSender.hpp
	FileServerReceiver.hpp	
	receiver.hpp
	sender.hpp
	subnet.hpp
bin [This folder will be created automatically the first time you compile the poject.
     It will contain all the executables]
build [This folder will be created automatically the first time you compile the poject.
       It will contain all the build files (.o) generated during compilation]
data_structures [This folder contains message data structure used in the model]
	message.hpp
	message.cpp
input_data [This folder contains all the input data to run the model and the tests]
	controlIn.txt
	fileserver_receiver_ackIn_test.txt
	fileserver_receiver_ackIn_test.txt
	fileserver_receiver_dataIn_test.txt
	fileserversender_ackIn_test.txt
	fileserversender_dataIn_test.txt
	fileserver_sender_input_test.txt
	fileserversender_requestIn_test.txt
	receiver_input_test.txt
	sender_input_test_ack_In.txt
	sender_input_test_control_In.txt
	subnet_input_test.txt
	requestIn.txt
	NoRequest.txt
simulation_results [This folder will be created automatically the first time you compile the poject.
                    It will store the outputs from your simulations and tests]
test [This folder the unit test of the atomic models]
	main_fileserverreceiver_test.cpp
	main_fileserverreceiver_test.cpp	
	main_receiver_test.cpp
	main_sender_test.cpp
	main_subnet_test.cpp
top_model [This folder contains the Offline_File_transfer_Simulation top model]	
	main.cpp
	
/*************/
/****STEPS****/
/*************/

0 - OfflineFileTransferSimulation.doc contains the explanation of this model

1 - Update include path in the makefile in this folder and subfolders. following lines need to be updated:
	INCLUDECADMIUM=-I ../../cadmium/include
	INCLUDEDESTIMES=-I ../../DESTimes/include
    	Update the relative path to cadmium/include from the folder where the makefile is. You need to take into account where you copied the folder during the installation process
	Example: INCLUDECADMIUM=-I ../../cadmium/include
	Do the same for the DESTimes library
   
2 - Compile the project and the tests
	2.1 - Open the terminal (Ubuntu terminal for Linux and Cygwin for Windows) in the Offline_File_Transfer_Simulation folder
	2.2 - To compile the project and the tests, type in the terminal:
		make clean; make all
3 - Run FILESERVERSENDER test
	3.1 - Open the terminal in the bin folder. 
	3.2 - To run the test, type in the terminal "./EXECUTABLE_FILE" (For windows, "./EXECUTABLE_FILE.exe"). 
		Example: ./FILESERVERSENDER_TEST (or ./FILESERVERSENDER_TEST.exe for Windows)
	3.3 - To check the output of the test, go to the folder simulation_results and open  "FileServerSender_test_output_messages.txt" and "FileServerSender_test_output_state.txt"
4 - To run FILESERVERRECEIVER_TEST, SUBNET_TEST, RECEIVER_TEST and SENDER_TEST tests you just need to select the proper executable name in step 3.2
			
5 - Run the top model
	5.1 - Open the terminal (Ubuntu terminal for Linux and Cygwin for Windows) in the bin folder.
	5.2 - To run the model, type in the terminal:
		./OFFLINE_FILE_TRANSFER ../input_data/controlIn.txt ../input_data/requestIn.txt (for Windows: ./OFFLINE_FILE_TRANSFER.exe ../input_data/controlIn.txt ../input_data/requestIn.txt)
	5.3 - To check the output of the model, go to the folder simulation_results and open "offlineFT_output_messages.txt" and "offlineFT_output_state.txt"
	5.4 - To run the model with different inputs
		5.1. Create new .txt files with the same structure as controlIn.txt or requestIn.txt in the folder input_data
		5.2. Run the model using the instructions in step 3
		5.3. Rename "offlineFT_output_messages.txt" and  "offlineFT_output_state.txt" to store any output result because it will be overwritten each time the simulation is run.




