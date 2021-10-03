# Proxy-Test-Tool
This project contains Test tool/ code for testing Internet Web proxy. This is created with the intension of helping Infrastructure/ Network/ Security engineers to troubleshoot Internet access issues through proxy
It's commonly observed that applications Azure bash, Git extension, NPM installer & similar non PAC aware applications fails to work behind corporate proxy. I observed this many times with Bluecoat ProxySG.

It's mostly because these applications fail to authenticate to the proxy & proxy blocks the connections. However, the developers usually don't agree to the this as they include proxy details in configuration file of the application. Issue is Proxy don't understand the format/ scheme these details are passed & blocks the connection.

This tool helps to check whether the proxy is blocking connection or the developer needs to adjust the parameters passed to the proxy.
