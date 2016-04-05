New systems are deployed by [downloading](http://dl.halon.se/vsp/) a disk image or virtual machine template. Existing systems are updated by simply pressing the automatic update button on the system's update page.

There is an [RSS feed](https://github.com/halonsecurity/changelog/releases.atom) available.

## 2.1.4.2
Released on 2009-12-22
- **`New`** Console in Web Administration (Diagnostics > Local Console)
- **`New`** Show licensed users in Web Administration and SOAP
- **`New`** Access Quarantine from Web Administration
- **`Imp`** 3rd-party components updated
- **`Imp`** in_network() now supports IPv4 and IPv6
- **`Imp`** dns() is now IPv6 ready, use dns4() or dns6() to choose
- **`Imp`** Improved compatibility with "tag subject" and non UTF-8
- **`Imp`** Colors in log search
- **`Imp`** Fixed MX-shuffle (rare round-robin delivery problem)
- **`Imp`** Delivery will only try the first three A/AAAA records
- **`Imp`** Selecting text in Web Administration logs
- **`Imp`** Many other improvements
- **`Bug`** Next retry wasn't presented in the local timezone
- **`Bug`** Rare bug while reverting between configurations
- **`Bug`** Could not save whitelist in Internet Explorer 8
- **`Bug`** Reload services when SSL certificate is updated
- **`Bug`** Retention policy in Web Administration was restricted to 32-letter
- **`Bug`** Adding one's own domains as domain alias confused quarantine
- **`Bug`** Spelling corrections
- **`Bug`** Overall stability fixes

## 2.1.4.1
Released on 2009-11-06
- **`Bug`** Better handling of questionable SMTP responses.
- **`Imp`** Russian and German in VSP's Getting Started.
- **`Imp`** Spam Assassin size limited raised to 500KiB.
- **`Imp`** Charset detection for Korean and other Asian languages.
- **`Bug`** Scripting error for Anti-Virus block in Content Flow.
- **`Bug`** Web Administration bug in Gettings Started for IE6/7.
- **`Imp`** Flow blocks in IP Policy log their results.
- **`Bug`** Japanese may now be default language in Quarantine.
- **`Imp`** Statistic's performance is improvements.
- **`Imp`** HSL does not resolve \$var to the value of $var.
- **`Imp`** HSL function eval() implemented.
- **`Imp`** Overall improvements in functionality and reliability.

## 2.1.4
Released on 2009-10-21
- **`Warning`** Storage disk must be at least 2GB for all units and configurations
- **`Imp`** Automatic initialization of new Storage disks for VSP/SPG
- **`Imp`** Firmware updates by self hosted Web Updates
- **`Imp`** Getting Started -guide in Console and Web Administration
- **`Imp`** IPv6 support in Web Administration
- **`Imp`** Keep current search in History/Queues while browsing and performing actions
- **`Imp`** IP-address whitelist in Content-Flow
- **`Imp`** Quarantine action "Empty" only empties the selected folder
- **`Imp`** Japanese language support in Quarantine
- **`Bug`** If no MX is found, try to use the A/AAAA record
- **`Bug`** SNMP and NTP problems with reconfiguration
- **`Imp`** 3rd party components updated
- **`Imp`** Overall improvements in functionality and reliability

## 2.1.3.1
Released on 2009-08-09
- **`Imp`** Overall improvements in functionality and reliability

## 2.1.3.2
Released on 2009-08-09
- **`Imp`** Overall improvements in functionality and reliability

## 2.1.3
Released on 2009-07-10
- **`Imp`** Throughput vastly improved, read the [guidelines](http://wiki.halon.se/Mail_Gateway_Performance)
- **`Imp`** Option to disable internal statistics and history
- **`New`** New [HSL](http://wiki.halon.se/HSL) functions
- **`Imp`** Overall improvements in functionality and reliability

## 2.1.2
Released on 2009-06-25
- **`New`** SNMP monitoring; custom MIB with statistics and information
- **`Bug`** Fixed Kaspersky engine error
- **`Imp`** Truncate configuration from CLI to save memory
- **`Bug`** Cache timeout set at execution instead of completion
- **`Imp`** IP Policy may also block UDP packets ($protocol)
- **`Imp`** Removed start-up related warnings
- **`Bug`** http() function can handle more than 10 parameters
- **`Imp`** Exceptions in Recipient Flow are reported as Defer()
- **`Imp`** Global quarantine admin users may blacklist globally
- **`Imp`** Blacklist handles domains and wildcard (%@domain)
- **`Imp`** Notify senders that they are blacklisted
- **`Imp`** Re-arranged tabs into new system menu in Web Admin.
- **`Bug`** Redirection bug when accessing a HTTPS interface using HTTP
- **`Bug`** Configuration upgrade for remote systems could cause timeouts
- **`Imp`** Better transport-lookup for messages generated internally
- **`Imp`** Mail function GetRoute() in HSL improved
- **`Imp`** Array function array_reverse() in HSL
- **`Imp`** Rate control function rate() in HSL
- **`Imp`** Rate control module in Recipient and Authentication Flows
- **`Imp`** Default message rate for authenticated users is 100 msg/h
- **`Imp`** HSL may cache results per message/session
- **`Imp`** Overall improvements in functionality and reliability

## 2.1.1
Released on 2009-06-03
- **`New`** Advanced options on Mail Content Flow with custom rules
- **`Imp`** Larger history (100.000 msgs.) for small disks (4 GB)
- **`Imp`** Anti-virus and Pattern Analysis (SA) results in history
- **`Imp`** Quarantine allows users to download messages
- **`Imp`** Quarantine web interface scales content to browser size
- **`Imp`** Quarantine accepts LDAP sign-in using alias as username
- **`Imp`** Quarantine has Korean translation
- **`Imp`** Quarantine displays outgoing queue
- **`Imp`** Quarantine displays folder's message count on mouse over
- **`Imp`** SPF module has trusted forwarders white-list field
- **`Imp`** Option to reject messages with virus
- **`Imp`** Recipient Flows reports the reason for rejection to sender
- **`Imp`** Overall performance and reliability improved
- **`Bug`** Quarantine now shows attachments correctly
- **`Bug`** Delivery forced default transport during certain circumstances
- **`Bug`** Quarantine now honors the LDAP version setting
- **`Bug`** It is now possible to mix recipient flows with "disabled"

## 2.1
Released on 2009-05-18
- **`Imp`** New Quarantine with LDAP support and Clustering
- **`Imp`** Administrator can access the Quarantine using their credentials
- **`Imp`** Quarantine has administrator-only folders (invisible to users)
- **`Imp`** Reporting > Real Time Log displays Anti-Virus, LDAP, etc.
- **`Imp`** The console's startup screen displays IP address
- **`Imp`** FTP access requires full [permissions](http://wiki.halon.se/Administration) or the "f"-flag
- **`Imp`** Administrators cannot change their own permissions
- **`New`** Added "null" transport (discards messages)
- **`Imp`** VMware ESXi users need to resize the disk during install
- **`Imp`** Added "Per Domain" for the SMTP Recipient Flow lookup module
- **`Bug`** Trace configuration revisions changes by administrator user.
- **`Imp`** Recipient Flows are per-domain instead of per-incoming.
- **`Imp`** Improved queue/history management responsiveness
- **`Imp`** Performance optimizations
- **`Imp`** 3:rd Party Components Updated
- **`Imp`** CLI command "version" displays appliance information
- **`Imp`** Overall performance and reliability improved

## 2.0.9
Released on 2009-03-24
- **`New`** Import Configuration from Clipboard
- **`Bug`** Installer on Windows 2000
- **`Bug`** Installer field validation
- **`Imp`** Warning on VMware Configuration Import
- **`Imp`** Repair License in Web Admin.
- **`Bug`** History Page in Internet Explorer fixed
- **`Imp`** Changes in terminology (Process Flow = Content Flow, etc)
- **`Bug`** Long lines message bug fixed
- **`New`** Implemented [cache [] function();](http://wiki.halon.se/HSL/Core/Control_Structures#cache)
- **`Bug`** IP Policy cache is now cleared properly
- **`Imp`** Web Admin. Script fields is monospace and support [tab]
- **`New`** Added !~ (negated regular expression) matching
- **`Imp`** Updates 3d-party libraries
- **`New`** Caches the Incoming's smtp_rcpt_lookup
- **`Imp`** Clear [cache](http://wiki.halon.se/HSL/Core/Control_Structures#cache) button (Mail Gateway -> Settings)
- **`Bug`** Non-UTF-8 bug (Mail Gateway -> Activity)
- **`Imp`** IP Policy performance improved
- **`Bug`** HTTP re-configured during address change
- **`Imp`** Removed reverse DNS lookups
- **`Bug`** Memory storage capacity resolved
- **`Bug`** Authentication and Recipient Flow re-configuration
- **`Bug`** NTP producing false error messages
- **`Imp`** Autodetect language in Web Admin.
- **`Imp`** Mail Content Flow didn't virus-check spam messages
- **`Imp`** Overall improvements and stability

## 2.0.8
Released on 2009-02-27
- **`Imp`** Firmware Update with step-by-step guide
- **`Imp`** VSP Installation with quick-start guide
- **`Imp`** "Paging" in Mail Gateway Activity tabs
- **`New`** dnstxt(), dnsmx() and implode() functions in [HSL](http://wiki.halon.se/HSL)
- **`Bug`** 500-errors handled correctly
- **`New`** Support for [alternative DNS](http://wiki.halon.se/Mail_Gateway#Lookup_MX) in lookup-mx
- **`Bug`** Handle UTF-8 in Tag Subject i Mail Flow
- **`New`** More languages added
- **`Imp`** Graph directions changed (left to right)
- **`Imp`** More SMTP debugging
- **`New`** [Direct Processing](http://wiki.halon.se/Mail_Gateway/Direct_Processing) gives reject function
- **`New`** Reject() function in Mail Flow
- **`Imp`** Set concurrent connections per Incoming (server)
- **`Imp`** Function declaration and "include" support in [HSL](http://wiki.halon.se/HSL)
- **`Imp`** Full UTF-8 support
- **`Imp`** Overall improvements and stability

## 2.0.7.1
Released on 2009-01-16
- **`Imp`** SMTP/LDAP SMTP authentication support
- **`Bug`** Disk Operation Stability
- **`Imp`** Storage Management (backup and restore)
- **`Imp`** Add multiple domains from Web Admin
- **`Imp`** Authentication and Recipient Flows
- **`Imp`** Many new functions added to HSL (see Wiki)
- **`Imp`** Secure Disk Wipe from Recovery Console
- **`Imp`** Send test mail to administrator from Web Admin
- **`Imp`** Reset Statistics in Web Admin
- **`Bug`** DNS/MX resolving
- **`Imp`** Authentication in Outgoing Transports
- **`Imp`** Preview mail in Quarantine
- **`Bug`** Quarantine handles quoted-printable
- **`Bug`** Quarantine reports handles quoted-printable
- **`Imp`** Warn users when Quarantine getting full
- **`Imp`** Scripting Testing Tool
- **`Imp`** Searching logs indicates when showing realtime
- **`Imp`** Custom icons for script blocks in Web Admin
- **`Imp`** Improved anti-virus detection
- **`Imp`** SOAP Interface improvements
- **`Imp`** Better Default Flows
- **`Bug`** Resolved back-to-default-config bug

## 2.0.6.2
Released on 2008-11-25
- **`Bug`** Quarantine templates

## 2.0.6.1
Released on 2008-11-20
- **`Bug`** Quarantine templates

## 2.0.6
Released on 2008-11-12
- **`Imp`** Send Domain Reports from Web Admin
- **`Bug`** Domain Statistics reported correctly (lowercase)
- **`Bug`** Overall Web Admin reliability
- **`Imp`** LDAP debugging
- **`Imp`** Mail throughput performance vastly improved
- **`Imp`** SPF Query Tool in Web Admin
- **`Imp`** in_network() now supports IP-ranges in HSL
- **`Imp`** Block() may send reason for blocking in HSL
- **`Imp`** dnsptr() to lookup PTR (ipv4 and ipv6) in HSL
- **`Imp`** 5 s timeout for dns() request by default in HSL
- **`Imp`** in_file() function (eg. black/white-lists) in HSL
- **`Imp`** First comment in a Flow Script shown as title
- **`Imp`** Customize generated e-mail
- **`Imp`** Multiple LDAP servers on incoming listerners
- **`Imp`** Default contact changed to "Postmaster"
- **`Imp`** Multidimensional arrays in HSL
- **`Bug`** Overall reliability and functionality
- **`Imp`** Quarantine translated to Swedish and customizable
- **`Imp`** Better default mail gateway Process Flow

## 2.0.5
Released on 2008-08-21
- **`Imp`** Improved quarantine with reports
- **`Imp`** Statistics in Web Administration
- **`Imp`** Domain reports with additional statistics
- **`Imp`** Logging is separated and improved
- **`Imp`** Message tracking (Activity)
- **`Imp`** Web Administration re-organization
- **`Bug`** Storage recovery from power failures
- **`Imp`** Certificate tunable "Optional but Verify"
- **`Imp`** Error messages are displayed as dialogues
- **`Imp`** Generate SSL certificates (Diagnostics section)
- **`Imp`** Name (tag) configuration revisions
- **`Imp`** SOAP configuration API (using WSDL file)
- **`Imp`** NFS replaces SMB for network storage
- **`Imp`** Graceful shutdown and restart
- **`Imp`** Boot procedure with progress and log
- **`Imp`** Multidimensional arrays in HSL
- **`Imp`** Headers are UTF-8 decoded in HSL
- **`Imp`** GetDSN(), GetRoute(), DeliverAsSpam() in HSL

## 2.0.4.1
Released on 2008-06-09
- **`Bug`** Web Administration error on factory reset units
- **`Imp`** Added German and Japanese language support
- **`Imp`** HSL Scripting in Outgoing Queue
- **`Imp`** Domain name variable in HSL
- **`Imp`** WrapMessageAddHeader function added in HSL
- **`Imp`** Revert to default config upon fatal errors
- **`Imp`** Disable Incoming Listeners upon storage failure
- **`Imp`** Regular Expression modifiers in HSL
- **`Imp`** Initial Access Control Flow statistics
- **`Imp`** Incoming Queue shows entire message
- **`Imp`** http() and explode() functions added to HSL
- **`Imp`** Pattern Analysis (spam assassin) module added
- **`Imp`** LDAP testing on Diagnostics section
- **`Bug`** Max Message Size can be increased
- **`Bug`** Overall reliability and functionality

## 2.0.3
Released on 2008-05-15
- **`Imp`** Added Italian, Spanish and Korean language support
- **`Imp`** Overall reliability improved

## 2.0.2
Released on 2008-05-12
- **`Bug`** SPF calculated $spamscore incorrectly
- **`Imp`** Reboot to Update Firmware from Web Admin.
- **`Bug`** Removed extra newline in messages
- **`Bug`** Database conversions could fail
- **`Imp`** Ability to disable ACL flow for services
- **`Bug`** NTP synchronization problem solved
- **`Imp`** Model-specific performance optimizations
- **`Bug`** Recovery from power failure
- **`Bug`** Windows (SMB) share no longer fails
- **`Imp`** Added date/time functionality to HSL
- **`Imp`** Overall reliability improved

## 2.0.1
Released on 2008-04-28
- **`Bug`** Problems in the parser of the mail scanner are fixed
- **`Bug`** Ajax problems in the mail processing flow are fixed
- **`Imp`** New functions in HSL (Halon Scripting Language)
- **`Imp`** UTF-8 support in HSL
- **`Bug`** Internet Explorer and Opera support
- **`Imp`** Overall reliability improved
