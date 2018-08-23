# delft3d6906
Dockerfile for Delft3d Tagged version 6906

1. Change directory to location of Dockerfile
	
	```
	cd ~/Documents/Docker/Delft3d
	```

2. Checkout tags version 6906
	
	```
	wget --user=[user_name] --password=[user_password] -r --no-parent https://svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/6906/
	```

3. Move tagged version 6906 to main directory
	
	```
	mv ~/Documents/Delft3d/svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/* ~/Documents/Delft3d/
	```

3. Get Dockerfile from Docker hub and place in the main directory with the Delft3d tagged version.
  *This should be done manually then select one of the two below options*

	-Option 1: Stay in the main directory and "Build" docker image of version 6906 and save it as "delft3d:6906"
		
		```
		docker build -t delft3d:6906 .
		```

	-#Option 2: Pull image from dockerhub.
		
		```
		docker pull dukemoose/delft3d
		```

4. Run docker image "delft3d:6906" and save log files on local machine @ "~/Documents/Docker/Delft3d/deltares-delft3d/funny_logs6906"
	
	```
	docker run -ti -v ~/Documents/Docker/Delft3d/deltares-delft3d/funny_logs6906:/delft3d/src/logs delft3d:6906 /bin/bash 
	```

5. Navigate to desired input file, change file permissions and run.
*Note: Change permissions step not included here, but should be done manually.*
	
	```
	./run_file_name.sh
	```
