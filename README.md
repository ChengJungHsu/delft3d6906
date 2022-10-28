# delft3d6906
Dockerfile for Delft3d Tagged version 6906

1. Change directory to location of Dockerfile
	
	```
	cd ~/Documents/Docker/Delft3d
	```

2. Checkout tags version 6906 (alternative command : svn checkout https://svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/6906/)
	
	```
	wget --user=[user_name] --password=[user_password] -r --no-parent https://svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/6906/
	```

3. Move tagged version 6906 to main directory
	
	```
	mv ~/Documents/Delft3d/svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/* ~/Documents/Delft3d/
	```

3. Get Dockerfile from Docker hub and place in the main directory with the Delft3d tagged version.
  *This should be done manually then select one of the two below options*

	- Option 1: Stay in the main directory and "Build" docker image of version 6906 and save it as "delft3d:6906"
		
		```
		docker build -t delft3d:6906 .
		```

	- Option 2: Pull image from dockerhub.
		
		```
		docker pull dukemoose/delft3d:6906
		```

4. Run docker image "delft3d:6906", load files from parent working directory $(pwd) into the container location "/home". Create "log" directory in PWD to store Delft3d log files. Results will be saved in the PWD accordingly. Adjust directory location of d_hydro.exe in Delft3d run scripts could be required.
	
	```
	docker run -ti -v $(pwd):/home -v $(pwd)/logs:/delft3d/src/logs dukemoose/delft3d:6906 /bin/bash 
	```
	
5. Navigate to desired input file, change file permissions and run.
*Note: Change permissions step not included here, but should be done manually.*
	
	```
	./run_file_name.sh
	```
