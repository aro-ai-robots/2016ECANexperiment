# 2016ECANexperiment
ECAN experimentation utilizing a new HebbianLink updating agent.


Install all dependencies octool for ubuntu
For a quick start using Ubuntu version >= 14.04, use octool script.
get it by running
	wget http://raw.github.com/opencog/ocpkg/master/ocpkg -O octool && chmod +rx octool
Options that are available can be displayed by running
	./octool -h
To install all dependencies necessary to build OpenCog.
	./octool -rsdpcalv

Building Cogutils

	git clone https://github.com/aro-ai-robots/2016ECANexperiment/cogutils
	cd cogutils
	mkdir build
	cd build
	cmake ..
	make 
	sudo make install
	cd

Building Atomspace
	
	git clone https://github.com/aro-ai-robots/2016ECANexperiment/atomspace
	cd atomspace
	mkdir build
	cd build
	cmake ..
	make 
	sudo make install
	cd

Building Opencog 

	git clone https://github.com/aro-ai-robots/2016ECANexperiment/opencog
	cd opencog
	mkdir build
	cd build
	cmake ..
	make 
	cd

To Run Opencog(2016)

use this to build and run:
	cd opencog/experiments/attention
	gedit SentenceGenStimulateAgent.h
Comment out #include <opencog/attention/AttentionAgent.h> (by using // at the beginning of the line) exit this command by closing the GUI
	cd ../../build
      	make experiments && ./opencog/cogserver/server/cogserver -c ../experiments/attention/opencog.conf
        	
      	In new terminal:
		telnet localhost 17001
		start-ecan
		start-exp 4 10 100
	Let the experiment run until you have enough data
		shutdown
	*note* this creates a subfolder under the attention directory

Visualization
---run these before---
	sudo apt-get install python-matplotlib
	apt-cache search python3-matplotlib
	sudo apt-get install python3-matplotlib

After running an experiment:
	Copy the hebplot (and save), avplot, and split hebfiles into the newly created folder named with the type of equation used in the experiment.
	If you do not have them, download them here:
	If you downloaded the Master_Opencog you only need the save
	My_avplot.py    My_hebplot_save.py    My_hebplot.py    Split_hebfiles.py    
       		cd into the new folder that was created in the experiment in a terminal
		./split_hebfiles.py
		./my_hebplot.py hebtv_#_# & ----> Ex: ./my_hebplot.py hebtv_0_3 & 
	The my_hebplot_save.py will save a .pdf
	*Currently the av plot does not work*
		rm hebtv*     




