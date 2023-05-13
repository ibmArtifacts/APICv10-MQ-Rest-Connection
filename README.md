# APICv10-MQ-Rest-Connection  

This document will demonstrate a sample of creating an APIC API to PUT and GET messages on MQ using the MQ REST APIs.  

**Prerequisites**:  
- Access to APIC API Manager to create APIs.  
- MQ Cluster available and configured properly. This document will not go over MQ install/config.  
- MQ REST API enabled and properly configured: https://www.ibm.com/docs/en/ibm-mq/9.3?topic=api-getting-started-messaging-rest  
- MQ Endpoint for APIC to connect to.  
- Queue Manager Name.  
- Queue Name.  
- Username and Password to access the queue.  

## Creating the APIC API  
1. Create a new API in the APIM.
2. In the Gateway > Policies section, locate and assemble the operation-switch for a post and get operation. Then drag and drop a set-variable and invoke policy into each operation switch case as shown in the diagram.  
![image](https://github.com/ibmArtifacts/APICv10-MQ-Rest-Connection/assets/66093865/ffc3c1df-0bbf-42f3-9d9c-0c85b0ea1f82)  
3. The configuration for the POST case set-variable policy will set headers for the required MQ PUT call.  
![image](https://github.com/ibmArtifacts/APICv10-MQ-Rest-Connection/assets/66093865/b4417726-16f2-4413-810d-52cff224a908)  
4. The Invoke policy configuration is where the PUT endpoint, the username/password, and TLS client certificate profile (if applicable) will be input.  
In the diagram below, a sample of the Invoke Policy MQ inputs are displayed, along with url with properties set as MQ variables. The properties may be used to map different variables to different catalogs during runtime (https://www.ibm.com/docs/en/api-connect/10.0.5.x_lts?topic=sap-defining-catalog-specific-property-values).
![image](https://github.com/ibmArtifacts/APICv10-MQ-Rest-Connection/assets/66093865/75b56870-87f0-4f45-ad2f-a8de0e1e2ea5)  
