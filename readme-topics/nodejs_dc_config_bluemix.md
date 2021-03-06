# Configuring the data collector for Bluemix applications 

## Before you begin

If you want to connect the data collector to your on-premises Cloud APM server and you haven't configured the downloaded image during server installation, make sure that you have prepared the data collector package before you continue with the following procedure. For more details, see [Configuring the installation images](https://www.ibm.com/support/knowledgecenter/SSHLNR_8.1.4/com.ibm.pm.doc/install/install_agent_preconfig.htm).

## Procedure

To configure your Node.js data collector for your Bluemix application, complete the following steps:  
 
 1. In the `package.json` file of your application, add `"ibmapm":"^2.0.0"` to the `dependencies` section to reference this package.  

 2. In the beginning of your application main file, add `require('ibmapm');`. 
     > Tip: If you start your application by running the `node app.js` command, `app.js` is the main file of your application.

 3. In the `manifest.yml` file of your application or on the **Bluemix UI**, set the following environment variables to define the target server:  
    ```
    env: 
        APPLICATION_NAME=my_app //Optional.
        IBM_APM_SERVER_URL: https://APM_server_ip/hostname:443
        IBM_APM_KEYFILE_PASSWORD: base_64_encrypted_password
        IBM_APM_KEYFILE_URL: http://your_key_file_server/keyfile.p12
    ```
    The `APPLICATION_NAME` must be unique on the same host.  

 4. From the home directory of your Node.js application, run the following command:  

    ```
    cf push
    ```
    

**Parent topic:** [Node.js Data Collector for IBM Application Performance Management (APM)](../README.md)
