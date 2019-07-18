# check_cisco_power_supply 1.0

# License
 This nagios plugin is free software, and comes with ABSOLUTELY NO WARRANTY.
It may be used, redistributed and/or modified under the terms of the GNU
General Public Licence (see http://www.fsf.org/licensing/licenses/gpl.txt).

# What it does
* Using state of the art non-blocking/async IO (EV and Mojolicious)
* Using DNS Native non-blocking resolver !
* IPV6 ready !!!
* Proper error handling !
* Uses native SNMP methods( get and bulk get )
* Works with all cisco routers/switches (ASR/VXR/2900/8xx) tested
* For now, only SNMP v2c is supported !!!

# Usage:
check_cisco_power_supply [ -V|--version ] [-H|--hostname <host>]
[-C|--community <Username>] [-t|--timeout <timeout>]

`` -?, --usage | Print usage information ``

`` -h, --help | Print detailed help screen ``

``-V, --version | Print version information ``

 ``--host, -H | IP address or hostname of cisco device ``

 ``--community, -C | SNMP community``

 ``-t, --timeout=INTEGER |Seconds before plugin times out (default: 10) ``

 ``-v, --verbose | prints extensive debugging info to stderr ``


  **This plugin was not tested on Windows.**

  **Feel free to do so and report back !**

  **At least use perl version 5.20 !**


  ## Prerequisites (Linux and other derivates):
  ### Debian (Build essentials) needed for EV and Net::DNS::Native
  `apt-get install build-essential`
  ### Redhat (Devtools)
  `yum groupinstall 'Development Tools'`
  ## Installation of dependend modules
  ### Using cpan:
  `cpan Mojolicous EV Net::SNMP Net::DNS::Native Monitoring::Plugin Socket6`
  ### Using cpanm:
  `cpanm Mojolicous EV Net::SNMP Net::DNS::Native Monitoring::Plugin Socket6`
  ### Example output
  ```CISCO_POWER_SUPPLY OK - Host: 192.168.1.1 power-module 0/PS0/M1/SP => on(2) power-module 0/PS0/M0/SP => on(2)```
  #### Timeout error
  ```CISCO_POWER_SUPPLY UNKNOWN - SNMP Timeout (5s) connecting to host 192.168.1.1```

  ## Credits:
  * [Mojolicious realtime framework](https://mojolicious.org)
  * [EV](https://metacpan.org/pod/EV)
  * [Net::DNS::Native](https://metacpan.org/pod/Net::DNS::Native)
  * [Net::SNMP](https://metacpan.org/pod/Net::SNMP)
  * [Monitoring::Plugin](https://metacpan.org/pod/Monitoring::Plugin)
