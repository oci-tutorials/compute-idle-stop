# Stopping an idle Oracle Linux instance in Oracle Cloud

This sample script (compute-idle-stop.sh) has been developed to stop an idle Oracle Linux instance in Oracle Cloud to avoid wasting credits.
In this context, an instance is considered idle if there are no active SSH sessions for more than 24 hours - make sure this is applicable to your case before executing it to avoid unexpected behavior.
If an instance is considered idle, the script uses the InstanceAction API to send the "SOFTSTOP" action: see https://docs.cloud.oracle.com/iaas/api/#/en/iaas/20160918/Instance/InstanceAction for more details



# Usage
* Clone this repo in the cloud instance to stop if idle
* Edit the variables in the "TODO" section at the beginning of the compute-idle-stop.sh script
* Make compute-idle-stop.sh executable: chmod u+x compute-idle-stop.sh
* Run compute-idle-stop.sh in the background: nohup ./compute-idle-stop.sh &

# Sample API Response
This is an example of successful API Response - note `"lifecycleState" : "STOPPING"`
```{
  "availabilityDomain" : "mDbm:EU-FRANKFURT-1-AD-1",
  "compartmentId" : "ocid1.compartment.oc1..aaaaaaaa5smvt6rXXXXXXXXXXXXXXXXXpj7uhiwiu6xeeejy4zajmoeops5q",
  "definedTags" : { },
  "displayName" : "instance-20190204-1411",
  "extendedMetadata" : { },
  "faultDomain" : "FAULT-DOMAIN-2",
  "freeformTags" : { },
  "id" : "ocid1.instance.oc1.eu-frankfurt-1.abtheljrdph7okf3XXXXXXXXXXXXXXXXXa32b5pmh364wogcgbgz47diskaq",
  "imageId" : "ocid1.image.oc1.eu-frankfurt-1.aaaaaaaagbrvhgXXXXXXXXXXXXXXXXXhabmzhx763z5afiitswjwmzh7upna",
  "ipxeScript" : null,
  "launchMode" : "NATIVE",
  "launchOptions" : {
    "bootVolumeType" : "PARAVIRTUALIZED",
    "firmware" : "UEFI_64",
    "networkType" : "VFIO",
    "remoteDataVolumeType" : "PARAVIRTUALIZED",
    "isPvEncryptionInTransitEnabled" : true,
    "isConsistentVolumeNamingEnabled" : true
  },
  "lifecycleState" : "STOPPING",
  "metadata" : {
    "user_data" : "[Redacted]",
    "ssh_authorized_keys" : "[Redacted]"
  },
  "region" : "eu-frankfurt-1",
  "shape" : "VM.Standard2.2",
  "sourceDetails" : {
    "sourceType" : "image",
    "bootVolumeSizeInGBs" : null,
    "imageId" : "ocid1.image.oc1.eu-frankfurt-1.aaaaaaaagbrvhgXXXXXXXXXXXXXXXXXhabmzhx763z5afiitswjwmzh7upna",
    "kmsKeyId" : null
  },
  "timeCreated" : "2019-02-04T14:12:08.299Z",
  "agentConfig" : {
    "isMonitoringDisabled" : false
  },
  "timeMaintenanceRebootDue" : null
}```
