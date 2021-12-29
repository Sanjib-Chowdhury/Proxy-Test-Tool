# Proxy-Test-Tool
This project contains Test tool/ code for testing connectivity through Internet Web proxy. This is created with the intension of helping Infrastructure/ Network/ Security engineers to troubleshoot Internet access issues through proxy.
It's commonly observed that applications like Azure bash, Git extension, NPM installer & similar non PAC aware applications fails to work behind corporate proxy. Users report seeing 407 Proxy autentication required message or 403 proxy block.

It's because these applications fail to authenticate to the proxy & proxy blocks the connections. However, the developers usually don't agree to the this as they include proxy details in configuration file of the application/ environment variable etc. Issue is Proxy don't understand the format/ scheme these details are passed to it & blocks the connection.

This tool helps to check whether the proxy is blocking connection or the developer needs to adjust the parameters passed to the proxy.
