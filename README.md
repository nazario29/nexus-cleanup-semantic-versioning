# Nexus script to delete docker images based on semantic version
## Description
This script will delete all docker images that have a lower version than the semantic version that the user passes as argument, uses Nexus API to interact with the Nexus itself. 
This has been tested with Nexus versions from 3.17 to 3.44.

Also will prompt the user for the necessary information:
- `username` to access nexus
- `password` to access nexus
- `microservice_name` to delete the images
- `compare_version` to be used for compare

The information about `nexus_url` and `docker_repository` should be filled on the respective variables from `remove_dockerimages_by_semver.sh`

The script was adapted to be able to run even in `git bash` so it has some funny ways on how variables are iterated and populated :)
## Requirements
- username with at least delete access to `docker_repository` repository from Nexus `nexus_url`
- functions file together with the actual script `./remove_dockerimages_by_semver.sh`
- jq

## How to run the script: 
```
./remove_dockerimages_by_semver.sh
```
Before the script prompts you to deletes your images will create a file `microservice_name.txt` and will have all docker images + component id so the user could double check the docker images identified for deletion.