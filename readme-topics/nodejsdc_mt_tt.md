# Configuring method trace and transaction tracking
You can modify variables to enable/disable method trace and transaction tracking capabilities.
- For Bluemix applications, set the variables in the `manifest.yml` file or on the `Bluemix UI`.
- For local applications, set the variables in the `config.properties` file.
## Method trace
By default, method trace is enabled. To disable it, set the `KNJ_DISABLE_METHODTRACE` variable to `False`. 
## Transaction tracking
By default, transaction tracking is disabled. To enable it, set the `KNJ_ENABLE_TT` variable to `True`.


**Parent topic:** [Node.js Data Collector for IBM Application Performance Management (APM)](../README.md)
