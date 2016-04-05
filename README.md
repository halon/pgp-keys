New systems are deployed by [downloading](http://dl.halon.se/vsp/) a disk image or virtual machine template. Existing systems are updated by simply pressing the automatic update button on the system's update page.

There is an [RSS feed](https://github.com/halonsecurity/changelog/releases.atom) available.

## 2.3.2
Released on 2011-12-21
- **`Imp`** Quarantining informs sender; rejects (550) instead of accepts (220)
- **`Imp`** The SMTP recipient lookup forwards errors from the mail server
- **`Imp`** Removed the incoming mail queue
- **`Imp`** Show Script looks much better with colors and formatting
- **`Imp`** The getting started has an option to trust server (use as smart host)
- **`Imp`** Clustering operations are faster thanks to new `rpcmplexd`
- **`Imp`** Option to export list of users per domain
- **`Imp`** The reporting's pie charts reflects selected period (day/month)
- **`Imp`** The console supports page up/down
- **`Imp`** The log viewer (searchlog) is faster
- **`Imp`** Korean language updated
- **`Imp`** Support for Internet Explorer 10
- **`Bug`** Issue with quarantine's history and domain administrators resolved
- **`Bug`** Anonymous LDAP authentication issue resolved
- **`Bug`** Issue with HSL's in_network() resolved

## 2.3.1
Released on 2011-10-04
- **`New`** View and reset rate control (Diagnostics > Rate Control)
- **`Imp`** Improved support for KVM virtualization platforms
- **`Imp`** Disabled auto-scroll in logs on mouse scroll
- **`Imp`** Improved graphs (bandwidth graphs and layout)
- **`Imp`** HSL's GuessAttachmentType() is faster
- **`Bug`** Resolved issues when upgrading 2.3-series on first boot

## 2.3.0.4
Released on 2011-09-22
- **`Imp`** Quarantine automatically sanitizes input
- **`Imp`** Pattern analysis' update is run every 6th hour
- **`Bug`** Pattern analysis' update error reporting issue resolved

## 2.3.0.3
Released on 2011-09-14
- **`Bug`** Serial console issue on SPG-150 resolved

## 2.3.0.2
Released on 2011-09-02
- **`Bug`** LDAP synchronization issue resolved
- **`Bug`** Pattern analysis' bayesian filter issue resolved

## 2.3.0.1
Released on 2011-08-17
- **`Bug`** Updated list of time zones (some didn't exist)
- **`Bug`** Guessing of character set issue resolved
- **`Bug`** Pattern analysis (ScanSA) custom rules issue resolved

## 2.3
Released on 2011-08-02
- **`New`** Based on FreeBSD 8.2
- **`New`** Content Inspection (DLP), ScanDLP() function
- **`New`** File store with CSV editor, deprecates FTP, in_file() function updated
- **`New`** Support for VMware vmxnet adapters
- **`New`** View history in Quarantine interface
- **`New`** Show header modifications in Quarantine interface
- **`Imp`** Quarantine interface is now fully clustered (user creation)
- **`Imp`** Updated Commtouch RPD and GlobalView engines
- **`Imp`** Updated Kaspersky anti-virus engine
- **`Imp`** Option to reset SpamAssassin bayesian database
- **`Imp`** The mail() function has a plain-text option
- **`Imp`** Fullscreen editors has "import from file" functionality
- **`Imp`** VMware/serial console auto-logout after 10 minutes
- **`Imp`** Mail Gateway > Domain section tables show more information
- **`Imp`** Many small improvements in functionality and stability
- **`Bug`** Storage fallback to memory issue resolved
- **`Bug`** Issues with static routes resolved

## 2.2.6.3
Released on 2011-05-11
- **`Imp`** Web Administration improvements (translations, statistics)
- **`Imp`** HSL functions floor() and ceil() added
- **`Bug`** Fixed incorrect return type from round()
- **`Bug`** Kaspersky anti-virus regression issue solved

## 2.2.6.2
Released on 2011-05-05
- **`Imp`** Updated 3rd-party components (Commtouch, Kaspersky, etc.)
- **`Imp`** Overall reliability and performance improved

## 2.2.6.1
Released on 2011-04-06
- **`Bug`** Mitigating HSL data type issue

## 2.2.6
Released on 2011-03-31
- **`New`** IPv6 support in IP Policy Flows (added $family variable)
- **`New`** Automatic configuration truncation option (System > Configuration)
- **`Imp`** dnsbl() function now queries for IPv6 according to RFC5782
- **`Imp`** Improved the Web Administration with some new functionality
- **`Imp`** Internet Explorer 9 support in Web Administration
- **`Imp`** Improved phishing protection
- **`Imp`** Improved SMTP IPv6 handling (prioritized)
- **`Imp`** DSN messages now includes only message/rfc822-headers
- **`Imp`** DKIMWithDeliver() now returns 500-error on un-signable messages
- **`Imp`** Updated 3rd-party components (libc, postfix, htmlpurifier etc.)
- **`Imp`** Overall performance improved
- **`Bug`** Folders created on FTP did not appear until after a reboot
- **`Bug`** IP Policy Flow's $serverport variable was not a number (string)
- **`Bug`** dnsptr() now supports compressed IPv6 addresses
- **`Bug`** Kaspersky's logfile not available on first run
- **`Bug`** Web Administration over IPv6 was partly broken
- **`Bug`** smtp_lookup_\*() should not use transport fallbacks
- **`Bug`** Quarantine() function did not honour SetMailTransport()

## 2.2.5.2
Released on 2011-02-10
- **`New`** Prioritized queues (per mail transports)
- **`New`** IO statistics tool in Web Admin (iostat)
- **`Imp`** Updated 3rd-party components (clamav)
- **`Imp`** Overall reliability and performance improved
- **`Bug`** BATV format bug
- **`Bug`** Deliver to A/AAAA records did not load balance properly

## 2.2.5.1
Released on 2011-01-24
- **`New`** VMware Zimbra integration in quarantine
- **`New`** Custom authentication with System Authentication Script
- **`New`** RADIUS (rad_authen) function for System Authentication
- **`New`** TACACS+ (tacplus_authen and tacplus_author) functions
- **`New`** Context-aware help (links to the doc. wiki) in Web Admin.
- **`Imp`** Updated 3rd-party components (ctipd, syslog, clamav, php)
- **`Imp`** Include kernel debugging in logs
- **`Imp`** Quarantine > Users, double-click users to 'sign as' as them
- **`Imp`** Activity > Logging has time interval option for faster searching
- **`Imp`** Some HSL functions are cached per default (per-message)
- **`Imp`** Admins can change quarantine users' passwords
- **`Imp`** Force web browsers to update cache on H/OS upgrades
- **`Imp`** HSL arrays may be initiated with [ ] instead of array()
- **`Imp`** LDAP debugging command hides passwords
- **`Imp`** Sort user's joined accounts in quarantine
- **`Imp`** Support for [IPv6 address]:port in network tools
- **`Imp`** New strnatcmp JavaScript library for better natural ordering
- **`Bug`** GlobalView, etc. stability improved with glibc patch
- **`Bug`** Fixed host name length (was limited to 32)
- **`Bug`** Fixed SMTP DNS lookup implementation misbehaviour
- **`Bug`** Heartbeat probe for Spam Assassin to resolve locks
- **`Bug`** Fixed missing SSL chain for certificates
- **`Bug`** Fixed multiple pages bug in Activity section of Web Admin.
- **`Note`** Configuration key config_user renamed to to system_user
- **`Note`** Signed in account used to browse cluster in Web Admin.
- **`Note`** Admin. accounts must use @local for quarantine sign-in

## 2.2.4
Released on 2010-11-25
- **`Imp`** Performance optimizations on message delivery
- **`Imp`** Double-click on messages to display text log
- **`Imp`** Version history information button on update section
- **`Imp`** Option to enable ATA write-cache
- **`Imp`** Non-blocking Kaspersky anti-virus database update
- **`Imp`** Getting Started allows example.org and another domain
- **`Imp`** Display newly added quarantine branding
- **`Imp`** GlobalView is logged as ctipd instead of [ctipd]
- **`Imp`** Unified authentication scheme
- **`Imp`** Updated 3rd-party components
- **`Imp`** Database errors are logged
- **`Bug`** Memory usage was erroneously calculated
- **`Bug`** Value rounding in reporting charts
- **`Bug`** Forbid domains ending with a dot
- **`Bug`** Flow selection race-condition for first message resolved
- **`Bug`** Memory leak in mailscand resolved
- **`Bug`** Spelling corrected in web administration
- **`Bug`** Overall reliability and performance improved

## 2.2.3
Released on 2010-10-25
- **`New`** Storage disk migration section
- **`New`** Unique self-signed certificate during install
- **`New`** New DirectDeliver() function to deliver inline
- **`New`** RPC log for SOAP API calls
- **`New`** Puny-codes for domains and in calculator
- **`Imp`** Much improved logging with session tracking
- **`Imp`** Graphical fixes for iPhone/iPad
- **`Imp`** Cluster administration performance improved
- **`Imp`** Updated 3rd-party components
- **`Imp`** User count for license in mailscand
- **`Imp`** Option to skip Getting Started
- **`Imp`** Russian language in quarantine
- **`Imp`** Overall graphical improvements
- **`Imp`** Improvements in flow presentation
- **`Imp`** Forbid non-ascii e-mail addresses
- **`Imp`** HSL function get_defined_functions()
- **`Imp`** TLS settings in smtp_lookup_rcpt/auth
- **`Imp`** Updated statistics to BIGINT
- **`Bug`** ClamAV could be started twice
- **`Bug`** LDAP search cached non-existent users for 24 hours
- **`Bug`** SNMP could fail to get ippolicyd statistics
- **`Bug`** Inventory keys denied for read-only users
- **`Bug`** ippolicyd could report statistics inaccurately
- **`Bug`** DNS failures (NXDOMAIN and NODATA) results in immediate bounce
- **`Bug`** Overall performance and stability improved
- **`Note`** It's recommended to empty your browser cache before signing on to your updated appliance
- **`Note`** It's not possible to downgrade to 2.2.2.2 or below (due to database upgrades)
- **`Note`** The log format is heavily changed, if you rely on machine parsed logging, be aware

## 2.2.2.2
Released on 2010-09-02
- **`Imp`** DNSSEC trusts newly signed root
- **`Imp`** CPU indicator in clustering overview
- **`Imp`** Simplified configuration management view
- **`Imp`** Remote systems alphanumerically sorted
- **`Imp`** Final actions terminate user defined functions
- **`Imp`** 3rd-party modules updated
- **`Imp`** Russian translations updated
- **`Bug`** HSL isset() function now works on arrays
- **`Bug`** IPv6 support in Syslog
- **`Bug`** Detect primary domain from Active Directory
- **`Bug`** Reporting tab timed out in large clusters
- **`Bug`** Overall performance and stability improved

## 2.2.2.1
Released on 2010-07-29
- **`New`** Novell GroupWise support in quarantine
- **`Imp`** 3rd-party components updated
- **`Bug`** Do not synchronize "fallback" configurations in cluster

## 2.2.2
Released on 2010-07-07
- **`New`** Backscatter protection with [BATV](http://wiki.halon.se/BATV)
- **`New`** Comments (C++ style, //) in address lists in web administration
- **`New`** Minger protocol recipient lookup function [minger_lookup()](http://wiki.halon.se/HSL_Core_Functions#minger_lookup.28.24host.2C_.24address.2C_.24options.29) in HSL
- **`New`** [SetRecipient()](http://wiki.halon.se/HSL_Mail_Content_Functions#SetRecipient.28.24recipient.29) function in HSL's Content Flow
- **`New`** HSL control structure "[barrier](http://wiki.halon.se/HSL_Control_Structures#barrier)" to do advanced synchronous scripting
- **`New`** HSL [isset()](http://wiki.halon.se/HSL_Core_Functions#isset.28.24variable.29) function, to check if a variable is defined or not
- **`New`** Set listen addresses for SSH, FTP and SNMP services
- **`New`** Prompted configuration download in web administration
- **`New`** Show configuration changes between revisions
- **`Imp`** Changed default IP to 169.254.1.1 (not to conflict with customer networks)
- **`Bug`** Do not allow recipient with trailing "." in the domain name

## 2.2.1.1
Released on 2010-06-17
- **`Bug`** A script validation error in Web Administration fixed
- **`Bug`** Syslog could fail at boot on rare occasions

## 2.2.1
Released on 2010-06-14
- **`Imp`** Show PKI information (X.509, private and public key)
- **`Imp`** Require passwords to be typed twice
- **`Imp`** Better TLS information in SMTP logs
- **`Imp`** DNSSEC and DNS cache made private in cluster
- **`Imp`** RPDAV icon changed to be distinguished from RPD
- **`Imp`** Show full AV, AS, LDAP and boot logs
- **`Imp`** Sort cluster nodes by name on Cluster > Overview
- **`Imp`** Support TLS/SSL for LDAP servers (Quarantine and HSL)
- **`Imp`** SMTP listener/transport support "internal-hostname" as hostname
- **`Imp`** More restrictive read-only users (no ping, etc)
- **`Imp`** Commands (ping, etc) in console are continuously updated
- **`Imp`** More private keys (Send to Server, etc)
- **`Imp`** 3rd-party components updated (ClamAV, etc)
- **`Bug`** RPDAV could not set "delete" action
- **`Bug`** View message button in outgoing queue fixed
- **`Bug`** No script errors for action on empty message queues
- **`Bug`** Graph X-axis could be a few seconds off in cluster
- **`Bug`** Failed to save flows when custom functions were used
- **`Bug`** Session timeout when saving services (SMTP, HTTP, etc)

## 2.2.0.1
Released on 2010-05-19
- **`Bug`** syslog needs to be restarted in order for hostname to be applied
- **`Bug`** If STARTTLS was announced but failed, optional TLS aborted
- **`Bug`** LDAP queries failed in HSL

## 2.2
Released on 2010-05-17
- **`New`** DNSSEC support and an internal DNS cache
- **`New`** DKIM signing and validation in Content flow
- **`New`** Reworked statistics with JavaScript graphs and a new layout
- **`New`** Show Script button on flows, displaying generated HSL code
- **`New`** Ability to write reject/defer messages in flow blocks
- **`New`** HSL variables $service (IP) and $messageid (Content) added
- **`New`** HSL functions file() and file_get_contents() added
- **`New`** Defer(), SetMailTransport() and AddHeader() in Content flow
- **`New`** Trusted (whitelist) block in Recipient flow
- **`New`** Web Administration organization with flows in one section
- **`New`** Unit identification used as internal hostname
- **`New`** Button for jumping to flows and profiles
- **`New`** Warning messages before discarding unsaved changes
- **`New`** Bookmarks to sections and tabs in Web Administration
- **`Imp`** Renamed processes to mailscand and mailqueued
- **`Imp`** Major performance improvement in mailscand
- **`Imp`** Overall performance from chunked statistic updates
- **`Imp`** Free-text search in Activity > Logging
- **`Imp`** Quarantine mail listing show scores and logging
- **`Imp`** Clustering menu and timeouts improved
- **`Imp`** E-mail file maintenance (lostfiles) added
- **`Imp`** Outbreak (RPDAV) anti-virus accuracy improved
- **`Imp`** Web Administration performance and caching improved
- **`Imp`** Updated 3rd-party components
- **`Imp`** Hop count in mailscand implemented
- **`Imp`** Overall performance and stability improved
- **`Bug`** SpamAssassin update bug resolved
- **`Bug`** SNMP label swapping bug resolved
- **`Bug`** Disabling of certain domains bug resolved
- **`Bug`** Zero-bitmask error in in_network() function resolved
- **`Bug`** IPv6 scope in network functions is now discarded
- **`Bug`** GMT timezone confusion on System > Time clarified
- **`Del`** Domain statistics reports removed
- **`Del`** Deprecated recipient databases migrated into flows
- **`Del`** Incoming listener (smtpd) doesn't listen to localhost
- **`Del`** Removed Deliver() as error fallback action
- **`Del`** Invalid PKI certificates no longer validates in config
- **`Del`** Deprecated $spamscore and LDAPLookup() removed
- **`Del`** Diagnostics > Troubleshooter tab removed

## 2.1.5
Released on 2010-03-01
- **`New`** Clustering of multiple SPG/VSP units
- **`New`** Graphical Console (replacing the CLI)
- **`New`** mail() function in HSL
- **`New`** GuessAttachmentType() in HSL
- **`Imp`** 3rd-party components updated
- **`Imp`** Quarantine reset password, does not send a new password, instead allows it to be changed
- **`Imp`** Overall improvements in functionality and reliability
- **`Imp`** HSL cache [] is not LRU per default (least recently used)
- **`Bug`** Domains were not disabled properly (nor alias domains)
- **`Bug`** IP Policy response were not always received
- **`Bug`** GetAttachmentName() were not decoded properly
- **`Bug`** Self-genrated messages had the wrong Content-Disposition
- **`Bug`** Unable to bind in queueprocessor (when custom source-ip was used)
- **`Bug`** Domain reports could take very long time to complete
- **`Bug`** Statistics could be collected for recipient instead of sender
- **`Bug`** Disk, CPU and Memory usage where 24 hours off in bar-indicator

## 2.1.4.4
Released on 2010-01-14
- **`Bug`** Issue with domains without MX records resolved
- **`Bug`** Internet Explorer 8 can now view message logs
- **`Bug`** Exporting users can now handle invalid UTF-8 chars

## 2.1.4.3
Released on 2010-01-07
- **`Imp`** Automatically format and use available disk (Xen and Hardware)
- **`Bug`** Xen could not leave firmware OS
- **`Bug`** Wrap-around long log lines in Web Administration
- **`Bug`** Rate-control would cause random reboots
- **`Bug`** GlobalView did not always start at boot
- **`Bug`** Newly downloaded SpamAssassin rules were not applied until reboot

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
