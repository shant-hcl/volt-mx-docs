---
layout: "documentation"
category: "voltmx_foundry_windows_install_guide"
---



Application Servers Prerequisites
=================================

Tomcat Prerequisites
--------------------

### How to Disable Weak Ciphers

To disable weak ciphers, modify the SSL Connector container attribute inside the `server.xml` with the required https connector tag details. The `server.xml` is located in the `<Install_Drive>\tomcat\conf` folder.

Add the following is a sample details to SSL connector tag:

{% highlight voltMx %}SSLEnabled="true" sslEnabledProtocols="TLSv1.2" ciphers="TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256, TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384, TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA,TLS_ECDHE_RSA_WITH_RC4_128_SHA, TLS_RSA_WITH_AES_128_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA,TLS_RSA_WITH_AES_256_CBC_SHA256, TLS_RSA_WITH_AES_256_CBC_SHA,SSL_RSA_WITH_RC4_128_SHA"
{% endhighlight %}

For example, the following is a sample modified https connector tag:

{% highlight voltMx %}<connector port="443" maxhttpheadersize="8192" address="127.0.0.1" enablelookups="false" disableuploadtimeout="true" acceptCount="100" scheme="https" secure="true" clientAuth="false" **SSLEnabled="true" sslEnabledProtocols="TLSv1.2" ciphers="TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256, TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384, TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA,TLS_ECDHE_RSA_WITH_RC4_128_SHA, TLS_RSA_WITH_AES_128_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA,TLS_RSA_WITH_AES_256_CBC_SHA256, TLS_RSA_WITH_AES_256_CBC_SHA,SSL_RSA_WITH_RC4_128_SHA"** keystoreFile="mydomain.key" keystorePass="password" truststoreFile="mytruststore.truststore" truststorePass="password"/>;
{% endhighlight %}

> **_Note:_** Upgrade the SSL Cipher list to the latest available versions.

### Heap and PermGen Settings

For Oracle Java 7 and Java 8, configure the heap settings for your application servers. In case of Oracle Java 7, you also need to configure PermGen settings. [Tomcat heap and PermGen settings](Troubleshooting.html#configuring-heap-and-permgen-size-for-tomcat)

> **_Note:_** From V8 SP4 FP1 HF1 onwards, Java 11 is supported for bundled Tomcat and JBoss servers.

JBoss Prerequisites
-------------------

### Heap and PermGen Settings

For Oracle Java 7 and Java 8, configure the heap settings for your application servers. In case of Oracle Java 7, you also need to configure PermGen settings. [JBoss Heap and PermGen settings](Troubleshooting.html#configuring-heap-and-permgen-size-for-jboss).

> **_Note:_** From V8 SP4 FP1 HF1 onwards, Java 11 is supported for bundled Tomcat and JBoss servers.

### Configuration of Database Driver Module

1.  Extract the  [com.zip](http://docs.voltmx.com/8_x_PDFs/com.zip)  file.

    The unzipped folder structure will be `com\mysql\main`.

2.  Stop the JBoss Application Server.
3.  For JBoss configured in the standalone mode, copy the extracted `com.zip` folder and place it in the  `{JBOSS_HOME}/modules/` path. For the domain mode, place the unzipped `com.zip` folder (`com\mysql\main\)` in the `{JBOSS_HOME}/modules/` path for each of the master/slave machines.

4.  Open and edit the appropriate configuration file based on the configured JBoss mode.

    For example, `domain.xml` in the domain mode and `standalone-full.xml` in the standalone mode. These files are available at `{JBOSS_HOME}/domain/configuration` and `{JBOSS_HOME}/standalone/configuration` folders respectively.

5.  Search for the `<subsystem xmlns="urn:jboss:domain:ee:4.0">` tag and add the appropriate global module based on the database selected.

    For example, add the following code for the domain mode:

    {% highlight voltMx %}<global-modules>  
    <module name="com.mysql" slot="main"/>  
    </global-modules>
    {% endhighlight %}
6.  Save the changes.
7.  Start the JBoss Server.

### Configure the Standalone Existing JBoss

To install Volt MX Foundry on an existing standalone JBoss, follow the steps to configure the standalone JBoss:

1.  Open the `standalone.xml` from the `<JBoss_Home>/standalone/configuration`.
2.  Configure Hostname/IP in the `standalone.xml` file for JBoss, as below:{% highlight voltMx %}	<interfaces>
    		<interface name="management">
    			<inet-address value="127.0.0.1"/>
    		</interface>
    		<interface name="public">
    			<inet-address value="<myHostName>"/>
    		</interface>
    	</interfaces>
    {% endhighlight %}
3.  Configure JBoss to listen for remote management requests as below:
    *   Add `<socket-binding name="management-native" interface="management" port="${jboss.management.native.port:9999}"/>` under the `<socket-binding-group>`
    *   Add following section under the `<management-interfaces>`{% highlight voltMx %}<native-interface security-realm="ManagementRealm">  
        <socket-binding native="management-native"/>  
        </native-interface>
        {% endhighlight %}
4.  For Engagement Services to work, remove the following subsystem:{% highlight voltMx %}<subsystem xmlns="urn:jboss:domain:jpa:1.1">
    <jpa default-datasource="" default-extended-persistence-inheritance="DEEP"/>|
    </subsystem>
    {% endhighlight %}

1.  In case of installing all the Volt MX Foundry components, follow these steps to increase heap size by setting the `JAVA_OPTS` in the `<JBOSS_DIR>\standalone\bin\standalone.sh/bat`:
    *   standalone.bat:{% highlight voltMx %}set "JAVA_OPTS= -server -Xms2048m -Xmx2048m"
        {% endhighlight %}
    *   **standalone.sh**:{% highlight voltMx %}JAVA_OPTS="-server -Xms1024M -Xmx1024M"
        {% endhighlight %}

### Configure the Log Locations - JBoss

To specify the log location where the logs for all Volt MX Foundry components will be generated, you must add the following parameter in the JVM arguments present in `standalone.bat/domain.bat`( for Windows) or `standalone.sh/domain.sh`(for Unix):

\-Duser.home="<log location>"

### Configure the Standalone Existing JBoss with Self-Signed Certificate (JBoss 7.1)

If you need to use existing JBoss with self-signed certificate, follow these steps:

1.  Add an Existing SSL Certificate to Cacerts. For more details, click [How to Add an Existing Secure Sockets Layer (SSL) Certificate]({{ site.baseurl }}/docs/documentation/Foundry/voltmx_foundry_windows_install_guide/Content/Post-Installation_Tasks.html#how-to-add-an-existing-ssl-certificate-to-cacerts).
2.  Copy the keystore file to `<JBoss_Home>/standalone/configuration` folder.

3.  Modify the `standalone.xml` by adding the following `security-realm` in the `security-realms` section.{% highlight voltMx %}   <security-realm name="WebSocketRealm">
                     <server-identities>
                            <ssl>
                                 <keystore path="<Keystore_file_name>" relative-to="jboss.server.config.dir" keystore password="<Keystore_password>"/>
                         </ssl>
                     </server-identities>
                </security-realm>                            

    {% endhighlight %}

    Here `<Keystore_file_name>` = Name of the keystore file. (for example, `keystore.jks`)`  
    <Keystore_password>` = Password of keystore file.


1.  In the standalone.xml, add the following `https-listener` tag for `default-server` in the Subsystem `urn:jboss:domain:undertow:3.1` .

    {% highlight voltMx %}<https-listener name="https" max-post-size="262144000" security-realm="WebSocketRealm" socket-binding="https"/>

    {% endhighlight %}

### Configure Port Settings for Multinode Loadbalancer Setups

Before installing Volt MX Foundry on an application server, for the application server to communicate with a Web Server properly, you must open the port 80.

#### How to Disable Weak Ciphers in JBoss

To disable weak ciphers, replace the `https-listener` under JBoss `subsystem/undertow`, for example, `<subsystem xmlns="urn:jboss:domain:undertow:3.1">`

For example, the following is a sample for https connector tag:

{% highlight voltMx %}<https-listener name="https" socket-binding="connect" security-realm="ApplicationRealm" verify-client="REQUIRED"/>
{% endhighlight %}

For example, the following is a sample modified https connector tag:

{% highlight voltMx %}<https-listener name="https" enabled-protocols="TLSv1,TLSv1.1,TLSv1.2" enabled-cipher-suites="SSL_RSA_WITH_3DES_EDE_CBC_SHA,SSL_DHE_RSA_WITH_3DES_EDE_CBC_SHA, TLS_RSA_WITH_AES_128_CBC_SHA,TLS_DHE_DSS_WITH_AES_128_CBC_SHA, TLS_DHE_RSA_WITH_AES_128_CBC_SHA,TLS_RSA_WITH_AES_256_CBC_SHA, TLS_DHE_DSS_WITH_AES_256_CBC_SHA,TLS_DHE_RSA_WITH_AES_256_CBC_SHA, TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA,TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA, TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA,TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA, TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA, TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA,TLS_ECDH_RSA_WITH_AES_128_CBC_SHA, TLS_ECDH_RSA_WITH_AES_256_CBC_SHA,TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA, TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA, TLS_ECDH_anon_WITH_3DES_EDE_CBC_SHA,TLS_ECDH_anon_WITH_AES_128_CBC_SHA, TLS_ECDH_anon_WITH_AES_256_CBC_SHA" verify-client="REQUIRED" security-realm="ApplicationRealm" socket-binding="connect"/>
{% endhighlight %}

WebLogic Prerequisites
----------------------

### Heap and PermGen Settings

Refer to [WebLogic heap and PermGen settings](Troubleshooting.html#configuring-heap-and-permgen-size-for-weblogic).

### Security Configurations

 To add environments to Volt MX Foundry Console, add the following configuration inside the  `security-configuration`  tag of the `config.xml` file of WebLogic Server.  

`<enforce-valid-basic-auth-credentials>false</enforce-valid-basic-auth-credentials>`  

After configuring the `security-configuration` tag, restart the server from WebLogic console. In case of WebLogic cluster, restart all servers from WebLogic console.

### Configure the Log Locations - WebLogic

To specify the log location where the logs for all Volt MX Foundry components will be generated, you must add the following parameter in the JVM arguments present in `bin/startWebLogic.cmd`( for Windows) or `bin/startWebLogic.sh`(for Unix):

    -Duser.home="<log location>"
