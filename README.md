# Proxy-Test-Tool
This is tool/ code for testing connectivity through Internet Web proxy. This is created with the intension of helping Infrastructure/ Network/ Security engineers to troubleshoot Internet access issues through proxy.
It's commonly observed that applications like Azure bash, Git extension, NPM installer & similar non PAC aware applications fails to work behind corporate proxy. Users report seeing 407 Proxy autentication required message or 403 proxy block.

It's because these applications fail to authenticate to the proxy & proxy blocks the connections. However, the developers usually don't agree to the this as they include proxy details in configuration file of the application/ environment variable etc. Issue is Proxy don't understand the format/ scheme these details are passed to it & blocks the connection.

This tool helps to check whether the proxy is blocking connection or the developer needs to adjust the parameters passed to the proxy.

Sample output below -

Date: 12/29/2021 16:26:34

Test URL: google.com

Proxy: http://testproxy.net:80

Method: GET


Response Headers:



StatusCode        : 200

StatusDescription : OK

Content           : 

RawContent        : HTTP/1.1 200 OK

                    X-XSS-Protection: 0
                    
                    X-Frame-Options: SAMEORIGIN
                    
                    Transfer-Encoding: chunked
                    
                    Proxy-Connection: Keep-Alive
                    
                    Connection: Keep-Alive
                    
                    Cache-Control: private
                    
                    Content-Type: text/html; ch...
                    
Forms             : 

Headers           : {[X-XSS-Protection, 0], [X-Frame-Options, SAMEORIGIN], [Transfer-Encoding, chunked], 

                    [Proxy-Connection, Keep-Alive]...}
                    
Images            : {}

InputFields       : {}

Links             : {}

ParsedHtml        : 

RawContentLength  : 0


Invoke-WebRequest : The maximum redirection count has been exceeded. To increase the number of redirections allowed, 

supply a higher value to the -MaximumRedirection parameter.

At line:52 char:12

+ $testurl = Invoke-WebRequest -Uri $url -Proxy $proxy @racfin -Method  ...
+            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (System.Net.HttpWebRequest:HttpWebRequest) [Invoke-WebRequest], Invali 
   dOperationException
    + FullyQualifiedErrorId : MaximumRedirectExceeded,Microsoft.PowerShell.Commands.InvokeWebRequestCommand
*******************************************************************

OCS Response:


HTTP/1.1 301 Moved Permanently

BFCache-Opt-In: unload

X-XSS-Protection: 0

X-Frame-Options: SAMEORIGIN

Proxy-Connection: Keep-Alive

Connection: Keep-Alive

Age: 1992929

Content-Length: 219

Cache-Control: public, max-age=2592000

Content-Type: text/html; charset=UTF-8

Date: Mon, 06 Dec 2021 14:51:05 GMT

Expires: Wed, 05 Jan 2022 14:51:05 GMT

Location: http://www.google.com/

Server: gws


<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">

  <TITLE>301 Moved</TITLE></HEAD><BODY>

  <H1>301 Moved</H1>

  The document has moved

  <A HREF="http://www.google.com/">here</A>.

  </BODY></HTML>


*******************************************************************

*******************************************************************

Page Source: <!doctype html><html itemscope="" itemtype="http://schema.org/WebPage" lang="en-GB"><head><meta content="text/html; charset=UTF-8" http-equiv="Content-Type"><meta content="/logos/doodles/2021/seasonal-holidays-2021-6753651837109324-6752733080595605-cst.gif" itemprop="image"><meta content="Festive Season 2021" property="twitter:title"><meta content="Festive Season 2021 #GoogleDoodle" property="twitter:description"><meta content="Festive Season 2021 #GoogleDoodle" property="og:description"><meta content="summary_large_image" property="twitter:card"><meta content="@GoogleDoodles" property="twitter:site"><meta content="https://www.google.com/logos/doodles/2021/seasonal-holidays-2021-6753651837109324-2xa.gif" property="twitter:image"><meta content="https://www.google.com/logos/doodles/2021/seasonal-holidays-2021-6753651837109324-2xa.gif" property="og:image"><meta content="1000" property="og:image:width"><meta content="400" property="og:image:height"><meta content="https://www.google.com/logos/doodles/2021/seasonal-holidays-2021-6753651837109324-2xa.gif" property="og:url"><meta content="video.other" property="og:type"><title>Google</title><script nonce="xw4ziXwe1LS7Z92yKFPL5A==">(function(){window.google={kEI:'O4zMYZPwJM7QaKeZnNAJ',kEXPI:'0,1302536,56873,6059,206,4804,2316,383,246,5,1354,4013,1237,1122516,1197748,642,27,380074,16114,19398,9286,17572,4858,1362,9291,3026,17582,4020,978,13228,3847,4192,6430,21822,919,5081,887,706,1279,2212,532,147,1103,840,6297,109,3405,606,2023,1777,520,14670,3227,2845,7,5599,6755,5096,16320,908,2,940,2615,13142,3,576,1014,1,5444,149,10045,1278,2652,4,1528,2304,7039,74,4610,18351,2038,2658,7357,30,13628,2305,2132,16786,2521,3306,2530,992,3102,17,3121,6,908,3,3541,1,11942,4582,283,38,874,5992,18443,2,14022,1931,92,692,255,2872,1678,744,5852,10463,1160,5678,1021,2381,2718,18261,2,1,6,7754,2124,2443,6256,6720,3699,82,2,1517,2,851,5758,4790,230,1,3,1,1017,6179,7490,3426,3707,1396,159,1360,1418,1216,1554,1616,494,1110,99,1329,514,1,1,923,484,1583,4152,3815,235,1892,2083,1152,217,1,682,3856,3,1241,318,741,6,2,389,361,388,2,31,69,608,1,1158,239,320,726,998,1358,4404,201,148,111,2,1158,2,90,101,831,311,29,1942,6,16,361,2,204,5,189,105,100,68,379,192,1185,179,2,324,2213,79,137,624,3199,71,5510012,189,257,590,1802426,4193852,259,2800438,882,444,1,2,80,1,1796,1,9,2553,1,748,141,795,563,1,4265,1,1,2,1331,4142,2609,155,17,13,72,139,4,2,20,2,169,13,19,46,5,39,96,548,29,2,2,1,2,1,2,2,7,4,1,2,2,2,2,2,2,353,513,186,1,1,158,3,2,2,2,2,2,4,2,3,3,269,1601,106,24,2,4,1,4,64,3,3,40,2,2,2,9,2,2,2,1,23952849,4041351,338,3,2414,1491,9,1435,159,1358,965,164,1,3596,3,2463,1933,831326',kBL:'4JUY'};google.sn='webhp';google.kHL='en-GB';})();(function(){
