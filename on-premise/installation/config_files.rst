Example Files
-------------

install.credentials
~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Credentials Setup ]

  dispatcherEncryptionKey=Zm7DLoK01^23t0R8Xc_NngLuiRZn%WQ7
  accessKey=zslJyB*O*x)mj[N0]w&1jpSEMoqjK]oba$oc
  encryptedManagementKey=73f30b959a961e9d399de716448dc93275d9ff
  firstEncryptedAccessKey=830e1b03a8e6e55edf53a75583c115dabc7b
  consoleEncryptionKey=J9r!flGcAbdmw$LbQgLN[_svDiz$GWnpjT2l]j
  secondEncryptedAccessKey=a23e18ef05d4fbf40b4f45886d1ce44cea8

  [ License Key ]
  LICENSE_KEY=asdf

  [Other Stuff]
  CONSOLE_URL=asdf
  CONSOLE_IP=asdf
  JAVA_HOME=/usr/lib/jvm/java-6-sun

  MYSQL_ROOT=trustno1


  [ KM Database Credentials ]

  kmDBUser=credentials
  kmDBPass=YVByJ6Qw4LyTZbj823VYNSAa52

  [ KM Configuration Files ]

  /services/km/tomcat/webapps/ROOT/META-INF/context.xml
  /services/km/tomcat/conf/server.xml

  [ KM Logging File ]

  /services/km/tomcat/logs/catalina.out

  [ provisioning Database Credentials ]

  provisioningDBUser=provisioning
  provisioningDBPass=Jy4eSWaS8iRU3IXvm8MmC7VD4M

  [ analytics Database Credentials ]

  analyticsDBUser=provisioning
  analyticsDBPass=Jy4eSWaS8iRU3IXvm8MmC7VD4M

  [ MQ ]

  mqUser=qsmq
  mqPassword=enstratus
  mqHost=localhost
  mqPort=5672


  KM_HOST=km

  SOURCE_CIDR=123.123.123.123

  [ Dispatcher Configuration Files ]

  /services/dispatcher/bin/tomcat
  /services/dispatcher/bin/enstratus
  /services/dispatcher/bin/pinger
  /services/dispatcher/tomcat/webapps/ROOT/META-INF/context.xml
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/mq.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-km-client.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-provisioning.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/dispatcher/tomcat/conf/server.xml

  [ Dispatcher Logging File ]

  /services/dispatcher/tomcat/logs/catalina.out

  PROV_HOST=dispatcher


  [ Monitor Configuration Files ]

  /services/monitor/bin/assign
  /services/monitor/bin/controller
  /services/monitor/bin/monitor
  /services/monitor/bin/pinger
  /services/monitor/classes/enstratus-km-client.cfg
  /services/monitor/classes/enstratus-provisioning.cfg
  /services/monitor/classes/mq.cfg
  /services/monitor/etc/cloud.properties
  /services/monitor/etc/monitors.cfg

  [ Monitor Logging Files ]

  /services/monitor/log/*.log

  [ Workers Configuration Files ]

  /services/worker/classes/dasein-persistence.properties
  /services/worker/classes/enstratus-km-client.cfg
  /services/worker/classes/enstratus-provisioning.cfg
  /services/worker/classes/worker.properties
  /services/worker/classes/mq.cfg
  /services/worker/bin/pinger
  /services/worker/bin/worker
  /services/worker/bin/publisher
  /services/worker/bin/subscriber

  [ Worker Logging File ]

  /services/worker/log/Subscriber.log

  [ Console Database Credentials ]

  consoleDBUser=console
  consoleDBPass=FHRMgSEUtdHNznT72ZGDZBRGjb
  enstratusConsoleDBUser=ens_console
  enstratusConsoleDBPass=6VsKF3Nathqayy0Uredd0WnKG0

  [ Console Configuration Files ]

  /services/console/bin/tomcat
  /services/console/bin/enstratus
  /services/console/tomcat/webapps/ROOT/META-INF/context.xml
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-webservices.cfg
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-console.cfg
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/custom/networks.cfg

  [ Console Logging File ]

  /services/console/tomcat/logs/catalina.out

  [ API Configuration Files ]

  /services/api/bin/tomcat
  /services/api/bin/enstratus
  /services/api/tomcat/webapps/ROOT/META-INF/context.xml
  /services/api/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-webservices.cfg
  /services/api/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/api/tomcat/webapps/ROOT/WEB-INF/classes/custom/networks.cfg

  [ API Logging File ]

  /services/api/tomcat/logs/catalina.out

