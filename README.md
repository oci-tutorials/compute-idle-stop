# Stopping an idle Oracle Linux instance in Oracle Cloud

This sample script (compute-idle-stop.sh) has been developed to stop an idle Oracle Linux instance in Oracle Cloud to avoid wasting credits.
In this context, an instance is considered idle if there are no active SSH sessions for more than 24 hours - make sure this is applicable to your case before executing it to avoid unexpected behavior.
If an instance is considered idle, the script uses the InstanceAction API to send the "SOFTSTOP" action: see https://docs.cloud.oracle.com/iaas/api/#/en/iaas/20160918/Instance/InstanceAction for more details



# Usage
* Clone this repo in the cloud instance to stop if idle
* Edit the variables in the "TODO" section at the beginning of the compute-idle-stop.sh script
* Make compute-idle-stop.sh executable: chmod u+x compute-idle-stop.sh
* Run compute-idle-stop.sh in the background: nohup ./compute-idle-stop.sh &
