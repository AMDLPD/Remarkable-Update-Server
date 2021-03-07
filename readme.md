# Simple Factory Reset (updater)

## Usage
get an official update e.g. [2.5.0.27](https://eu-central-1.linodeobjects.com:443/remarkable-2/build/reMarkable%20Device%20Beta/RM110/2.5.0.27/2.5.0.27_reMarkable2.signed), rename it to:

- for rm2: `update_rm2`
- for rm1: `update_rm1`

set the `update_version` in `serve.py` to `2.5.0.27` (will be fixed)  
and drop it in current folder  
start the server: `python serve.py`  

On the device, edit: `/usr/share/remarkable/update.conf`  
set the line: `SERVER=http://yourhost:8000`  
restart the update service: `systemctl stop update_engine`  
start the update engine: `update_engine -foreground`  
in a different shell: `update_engine_client -check_for_update`  

## TODO
read the version from the filename

## To switch the partition
use the `switch.sh` script on the device
