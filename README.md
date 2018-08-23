# delft3d6906
Dockerfile for Delft3d Tagged version 6906

# Change directory to location of Dockerfile
cd ~/Documents/Docker/Delft3d

# Checkout tags version 6906
wget --user=[User_name] --password=[User_password] -r --no-parent https://svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/6906/

# Move tagged version 6906 to main directory
mv ~/Documents/Delft3d/svn.oss.deltares.nl/repos/delft3d/tags/delft3d4/* ~/Documents/Delft3d/


# Get Dockerfile from github and place in directory with Delft3d tagged version.


# Option 1
### Stay in the main directory and "Build" docker image of version 6906 and save it as "delft3d:6906"
docker build -t delft3d:6906 .

# Option 2
### Pull image from Docker repository
docker pull dukemoose/delft3d


# Run docker image "delft3d:6906" and save log files on local machine @ "~/Documents/Docker/Delft3d/deltares-delft3d/funny_logs6906"
docker run -ti -v ~/Documents/Docker/Delft3d/deltares-delft3d/funny_logs6906:/delft3d/src/logs delft3d:6906 /bin/bash 

# Navigate to desired input file, change file permissions and run.
*Change permissions step not included here, but should be done manually.*
./run_file_name.sh
