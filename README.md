# mill-init
Scripts, templates, and other configuration for deploying the mill in the cloud.

This repo was seeded with the set of files that formerly lived in https://github.com/duracloud/mill/resources/userdata/ since the cloud-init config should be versioned independently from the mill itself. 

## How to generate cloud-init scripts for running in AWS EC2.

1. Create directories
    `mkdir -p myenv/{config,output}`
2. Copy environment props sample file and update with appropriate values:
 `cp sample-environment.properties myenv/config/environment.properties`
3. Copy the mill configuration sampple file and update with appropriate values:
  `curl https://raw.githubusercontent.com/duracloud/mill/master/resources/mill-config-sample.properties > myenv/config/mill-config.properties`
4. Run the python generate tool and follow the usages: 
   `./generate-all-cloud-init.py -m myenv/config/mill-config.properties -e myenv/config/environment.properties -o myenv/output` 
