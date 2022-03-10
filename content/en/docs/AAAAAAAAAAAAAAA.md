{
    "title": "AAAAAAAAAAAAAAA ",
    "linkTitle": "AAAAAAAAAAAAAAA",
    "weight": "5"
}
| Conversions | render |
| --- | --- |
| underscore | aaa_aaa_aaa |
| backslash + underscore | aaa\_aaa\_aaa |
| underscore g | aaa_gaaa_gaaa |
| backslash underscore g | aaa\_gaaa\_gaaa |
|  brackets | [CORE] |
| backslash brackets | \[CORE\] |
| 2 asterisks \*\*aaa\*\* | **aaa** |
| 3 asterisks  | ***aaa*** |
| 4 asterisks  | ****aaa**** |
| 5 asterisks  | *****aaa***** |
| 6 asterisks  | ******aaa****** |
| 7 asterisks \*\*\*\*\*\*\*aaa\*\*\*\*\*\*\* | *******aaa******* |
| 8 asterisks \*\*\*\*\*\*\*\*aaa\*\*\*\*\*\*\*\* | ********aaa******** |
| asterisks  \*\* \*\*aaa\*\* \*\* | ** **aaa** ** |
| asterisks  \*\*\* \*\*aaa\*\* \*\*\* | *** **aaa** *** |
| asterisks  \*\* \*\*\*aaa\*\*\* \*\* | ** ***aaa*** ** |
| asterisks mix \*\*\*aaa\*bbb\*\* | ***aaa*bbb** |
| asterisks mix \*\*\*\*aaa\*bbb\*\* | ****aaa*bbb** |
| asterisks mix \*\*\*\*aaa\*\*bbb\*\* | ****aaa**bbb** |
| asterisks mix \*\*\*\*aaa\*\*\*bbb\*\* | ****aaa***bbb** |
| \*\*[IDF \*\*]\*\*\*\* | **[IDF **]****  | 


aaa_aaa_aaa  aaa\_aaa\_aaa  aaa_gaaa_gaaa  aaa\_gaaa\_gaaa  [CORE]  \[CORE\] 


target name

1. Access the `/SentinelEventRouter/conf `directory.
1. Edit the `target.xml` file to route (`EDGEAGENT`).
    &lt;ol style="list-style-type: lower-alpha;">
1. Add the Edge Agent as a new target.  
    &lt;pre>
                    &lt;Target name="EDGEAGENT"  defaultXntf="no"  defaultXml="no">
              &lt;Access mode="QLT"  addr="&lt;Edge_Agent_IP_address>"  port="8002" />
            &lt;/Target>
        
1. Define a route to send the `XFBTransfer `Tracked Object to the Edge Agent.
