## Configuring on-premises Node.js applications monitoring using the Cloud APM server

There are two ways to configure the Node.js data collector for monitoring the local applications. One is to use the Cloud APM data collector package to install the Node.js data collector for your application. The other is to directly install appmetrics with the Node.js data collector integrated.

### Option 1: Using the Cloud APM data collector package
Detailed instructions can be found in IBM Cloud APM Knowledge Center. See [Configuring the data collector for local applications](https://www.ibm.com/support/knowledgecenter/SSHLNR_8.1.4/com.ibm.pm.doc/install/nodejs_config_dc.htm).


### Option 2: Installing appmetrics with the data collector integrated
Complete the following steps to install appmetrics with the Node.js data collector integrated:

1. In the `package.json` file of your Node.js application, add the following line to the dependencies section:
    <pre>"appmetrics":"^4.0.0"</pre>
    
2. Add the following line to the begining of the main file of your Node.js application:
    <pre>require('appmetrics');</pre>
    
    **Tip:** If you start your application by running the node app.js command, `app.js` is the main file of your application.

3. Enable the Node.js data collector by specifying the server connection information with **either** of the following methods:

- Option 1: Set the **APM_BM_GATEWAY_URL** environment variable to specify the Cloud APM server URL. The format is <code>https://<i>server ip or hostname</i>:443</code> or <code>http://<i>server ip or hostname</i>:80</code>.

- Option 2: Specify the Cloud APM server in the `\node_modules\ibmapm-embed\etc\global.environment` file.

**Tip:** For information about more supported environment variables, see [Customizing the Node.js data collector for on-premises applications](https://www.ibm.com/support/knowledgecenter/SSHLNR_8.1.4/com.ibm.pm.doc/install/customize_nodejs_dc.htm).

3. Run the following command to install all required dependencies:
    <pre>npm install</pre>

4. Restart the Node.js application.
