# Snaplogic plugin
Version 1.0.00

### Short description:
Control-M Integration plugin for Snaplogic.

Created on August-2021
 
### Detailed description:

The Snaplogic plugin for Control-M enables the integration of Snaplogic with the rest of your application 
ecosystem.

This integration will allow the ability to trigger a Snaplogic pipeline, and monitor it to completion.

#### Pre requisites

Control-M Version 9.20.000,
Fixpack 9.0.20.100,
Application pack Patch 9.0.20.101

Note: This plugin is compatible with bmc Helix Control-M

#### Features

* #### 1. Bearer Token (required for pipeline trigger)
* ####    Basic Token (required for monitor to completion)

![connprof](./images/connprof.png)

* #### 2. Trigger pipelines with parameters.

![jobparams](./images/jobparams.png)

* #### 3. Return the results of the pipeline steps to the output in the Control-M Monitoring domain.  

![output](./images/output.png)

* #### 4. Integrate Snaplogic pipeline runs with all existing Control-M capabilities.  
    For example : 
                   
        a. Have your pipeline tasks defined in JSON and managed by your cicd process.          
        b. Attach SLA's to your pipeline.
        c. Wait for a b2b source to arrive and process it in an application and run a pipeline based on the outcome.
        d. Attach prior and post dependancy steps to your pipeline for a fully encompassed view of your environment.
        e. A single reference point for the entire lifecycle of your data, from creation to analytics.

* #### 5. Automation API Connection Profile samples

##### Using Bearer Token and Basic Token
```
"PROFILENAME": {
    "Type": "ConnectionProfile:ApplicationIntegrator:AI SNAPLOGIC",
    "AI-Org": "SAMPLE_ORG",
    "AI-Basic Token": "*****",
    "AI-Bearer Token": "*****",
    "AI-Host": "elastic.snaplogic.com",
    "Description": "",
    "Centralized": true
}```

```

* #### 6. Automation API JSON job sample

```
{
  "folderName": {
    "Type": "SimpleFolder",
    "ControlmServer": "SERVER",
    "OrderMethod": "Manual",
    "AI SNAPLOGIC_Job_Name": {
      "Type": "Job:ApplicationIntegrator:AI SNAPLOGIC",
      "ConnectionProfile": "SNAPPROFILE",
      "AI-Project Name" : "SAMPLE_PROJECT_NAME",
      "AI-Pipeline Task Name" : "SAMPLE_PIPELINE_TASK",
      "Host": "hostname",
      "RunAs": "USER"
    }
  }
}
```



