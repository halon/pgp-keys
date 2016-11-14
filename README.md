New systems are deployed by [downloading](http://dl.halon.se/vsp/) a disk image or virtual machine template. Existing systems can be [updated](http://wiki.halon.se/Software_update) by (for example) simply pressing web admin's update button.

There is an [RSS feed](https://github.com/halonsecurity/changelog/releases.atom) available.

## 3.5-r5p4
Released on 2016-11-09
- **`Imp`** Updated system packages
 - FreeBSD 10.3-RELEASE-p11
 - FreeBSD 10 [quarterly](http://pkg.freebsd.org/freebsd:10:x86:64/quarterly/) packages
 - [CYREN](http://wiki.halon.se/CYREN) ctipd 4.0.36.1 and ctasd 5.0.88.1
- **`Bug`** HELO/EHLO hostname was not set for invalid domain names
- **`Bug`** Recipient limit was decreased compared to previous releases
- **`Bug`** License users export could fail

## 3.5-r5p3
Released on 2016-09-27
- **`Bug`** Updated to FreeBSD 10.3-RELEASE-p9 that fixes an [OpenSSL regression](https://www.freebsd.org/security/advisories/FreeBSD-SA-16:26.openssl.asc)

## 3.5-r5p2
Released on 2016-09-23
- **`Sec`** Updated to FreeBSD 10.3-RELEASE-p8 that fixes OpenSSL [CVE-2016-6304 and others](https://www.freebsd.org/security/advisories/FreeBSD-SA-16:26.openssl.asc)
- **`Imp`** Setting for and changes in `smtpd`'s log verbosity

## 3.5-r5p1
Released on 2016-09-08
- **`Imp`** Enabled TCP_NODELAY on SMTP client socket
- **`Imp`** More user friendly errors in mailQueueRetry, mailQueueDelete and mailQueueBounce API
- **`Imp`** Updated to htmlpurifier 4.8.0
- **`Bug`** Properly reload scripts with deleted include files when re-added
- **`Bug`** Fixed regressions with XCLIENT, implicit TLS and IP flow statistics

## 3.5-r5
Released on 2016-09-05
- **`New`** [ident_lookup()](http://docs.halon.se/hsl/functions.html#ident_lookup) function to lookup users over the ident protocol
- **`New`** `$senderport` in IP, RCPT TO and DATA context
- **`Imp`** Postfix is not longer the default MTA

## 3.5-r4
Released on 2016-08-29
- **`Imp`** Improvements in the [script editor](http://wiki.halon.se/HSL_editor)
 - Added support for matching closing brackets
 - Variable highlighting in strings
- **`Imp`** Updated system packages
 - [CYREN](http://wiki.halon.se/CYREN) ctipd 4.0.35.5
 - FreeBSD 10.3-RELEASE-p7
- **`Imp`** Improve detection of password protected ZIP files
- **`Bug`** Fixes in REST API and [SOAP](http://wiki.halon.se/SOAP) proxy
 - hslRate() regression with affected rate pie charts
 - mailQueue() regression with affected email tracking metadata display
- **`Bug`** Fix delivery to numeric MX with DANE

## 3.5-r3
Released on 2016-08-03
- **`New`** Added an interface for editing CSV files to the script editor
- **`New`** Added a revision-based diff utility to the script editor
- **`Imp`** Switched to Monaco (MS VC code) and enabled autocompletion
- **`Imp`** Added paging to the SOAP function `configRevisionLog`
- **`Imp`** Added retry functionality to background [http()](http://docs.halon.se/hsl/functions.html#http) requests
- **`Imp`** Added `extended_result` option to the [http()](http://docs.halon.se/hsl/functions.html#http) function
- **`Imp`** HSL now supports [keyed assignments](http://docs.halon.se/hsl/operators.html#destructuring-assignment) when destructing arrays
- **`Imp`** Updated system packages to the latest quarterly; such as
 - FreeBSD 10.3-RELEASE-p6
 - PHP 7.0.9
 - ClamAV 0.99.2
 - PostgreSQL 9.3.13
 - nginx 1.10.1
- **`Bug`** Failed [http()](http://docs.halon.se/hsl/functions.html#http) requests always returns `None` on errors
- **`Bug`** Always send an authentication header on "401" errors (fixes issue with some SOAP clients)
- **`Bug`** Web admin interface fixes
 - Increase timeout to prevent "504" timeout errors
 - File viewer couldn't show files larger than 2 GiB
 - Fixed a rare crash which chould occur with certain setups
- **`Dep`** Config key `mail_transport`'s parameter sasluser/pass renamed to saslusername/password
- **`Dep`** Config key `mail_server`'s parameter sasl_tls renamed to sasltls
- **`Dep`** Removed the [GuessAttachmentType()](http://wiki.halon.se/Deprecation#GuessAttachmentType) function

## 3.5-r2
Released on 2016-05-26
- **`Imp`** Switch to nginx and php-fpm (from Apache 2.4 and mod_php)
- **`Bug`** Fixed issue with reloading some configurations
- **`Bug`** Fixed regression in the new SOAP proxy which was introduced in 3.5-r1
 - getTime() had the wrong default UTC mode
 - It didn't handle 401 (Unauthorized) errors correctly
 - Cluster sync (clusterd) didn't work with pipes in configuration values
 - Cluster overrides couldn't be added

## 3.5-r1
Released on 2016-05-20
- **`New`** Added SOAP function mailQueueUpdateBulk to set various fields (`quarantine`, `transport`, etc.)
- **`New`** Added MIME.[getHeaderNames()](http://docs.halon.se/hsl/data.html#MIME.getHeaderNames) to the DATA MIME object
- **`Imp`** Added an option array to MIME.[get](http://docs.halon.se/hsl/data.html#MIME.getHeader)/[set](http://docs.halon.se/hsl/data.html#MIME.setHeader)/[delHeader()](http://docs.halon.se/hsl/data.html#MIME.delHeader) to address a specific header by index
- **`Imp`** Replaced gSOAP with a REST/JSON API and a PHP SOAP proxy for compatibility
- **`Bug`** Fix problem when clearing empty rate entries

## 3.5
Released on 2016-04-18
- **`New`** New [HSL scripting editor](http://wiki.halon.se/HSL_editor)
- **`New`** Added MIME.[send()](http://docs.halon.se/hsl/functions.html#MIME.send) to builtin MIME object
- **`New`** Added MIME.[getBody()](http://docs.halon.se/hsl/functions.html#MIME.getBody) to builtin MIME object
- **`New`** Added MIME.[toString()](http://docs.halon.se/hsl/functions.html#MIME.toString) to builtin MIME object
- **`New`** Added [`??`](http://docs.halon.se/hsl/structures.html#null-coalescing-operator) (null coalescing operator) to HSL
- **`New`** Added [`include_once`](http://docs.halon.se/hsl/structures.html#include-once) to HSL
- **`New`** Added [`object`](http://docs.halon.se/hsl/structures.html#object) and [`this`](http://docs.halon.se/hsl/structures.html#this) to HSL
- **`New`** Added [destructuring assignment](http://docs.halon.se/hsl/operators.html#destructuring-assignment) to HSL
- **`New`** Added support for [HAProxy](http://www.haproxy.org)'s proxy protocol
- **`Imp`** Based on [FreeBSD 10.3](https://www.freebsd.org/releases/10.3R/announce.html)
- **`Imp`** Disabled SSLv3 for inbound SMTP connections
- **`Imp`** Added support for `sourceip` as a `netaddr:X` in `smtp_lookup_rcpt()` and `smtp_lookup_auth()`
- **`Imp`** Updated components
 - [CYREN](http://wiki.halon.io/CYREN) RPD (ctasd) engine
 - FreeBSD 10 [quarterly](http://pkg.freebsd.org/freebsd:10:x86:64/quarterly/) packages
- **`Imp`** `Deliver()` and `Quarantine()` now supports an option array
- **`Bug`** Fix problem with partial updated Sophos databases
- **`Bug`** Fix problem with where the flow wasn't reloaded if a include file was changed
- **`Bug`** Fix problem with `mail()` where `transportid` wasn't used
- **`Bug`** Fix problem with IE11 and placeholders in flows
- **`Dep`** Undocumented `CopyMail()` and `DirectDeliver()` in favour of `Deliver()` arguments
- **`Dep`** Deprecated [GuessAttachmentType()](http://wiki.halon.se/Deprecation#GuessAttachmentType)
- **`Dep`** Removed [template support](http://wiki.halon.se/Deprecation#Templates) from the `mail()` function
- **`Dep`** Removed the [trigger URL](http://wiki.halon.se/Deprecation#Trigger_URL) configuration key from the quarantine
- **`Dep`** Removed the [Blacklist()](http://wiki.halon.se/Deprecation#Blacklist) function
- **`Dep`** Removed the [ScanBWList()](http://wiki.halon.se/Deprecation#ScanBWList) function
- **`Dep`** Removed the [ScanSPF()](http://wiki.halon.se/Deprecation#ScanSPF) function
- **`Dep`** Removed the <tt>deliver_type</tt> and <tt>deliver_args</tt> arguments from [DeliverWithDKIM()](http://wiki.halon.se/Deprecation#DeliverWithDKIM.27s_deliver_arguments)
- **`Dep`** Removed support for <tt>switch</tt> with [variable assignment](http://wiki.halon.se/Deprecation#Switch_with_variable)
- **`Dep`** Removed support for <tt>function</tt> without [argument list](http://wiki.halon.se/Deprecation#Functions_without_argument_list)
- **`Dep`** HSL returns None (instead of an empty string) when dereferencing a non-existing elements in arrays

## 3.4-r4p2
Released on 2016-03-02
- **`Sec`** Addresses the [DROWN](https://openssl.org/news/secadv/20160301.txt) vulnerability (CVE-2016-0800)

## 3.4-r4p1
Released on 2016-02-20
- **`Bug`** Fix regression in [CYREN](http://wiki.halon.se/CYREN)'s ctipd 4.0.32 (included in 3.4-r4) by rolling back to 4.0.31

## 3.4-r4
Released on 2016-02-16
- **`New`** [DATA](http://docs.halon.se/hsl/data.html) context [MIME](http://docs.halon.se/hsl/data.html#data.MIME) class for working with an email's body
- **`New`** Standard library [MIME](http://docs.halon.se/hsl/functions.html#MIME) class for creating MIME parts
- **`New`** [closures](http://docs.halon.se/hsl/structures.html#closure-functions) in addition to lambda functions
- **`New`** [dnscname()](http://docs.halon.se/hsl/functions.html#dnscname) function to resolve CNAME records (RR)
- **`New`** [is_function()](http://docs.halon.se/hsl/functions.html#is_function) function to check if data is a function
- **`New`** [array_sort()](http://docs.halon.se/hsl/functions.html#array_sort) function to sort arrays
- **`New`** [HSL cache](http://docs.halon.se/hsl/structures.html#cache) statistics in [SOAP](http://wiki.halon.se/SOAP) and web admin
- **`Imp`** The [ScanDLP()](http://docs.halon.se/hsl/data.html#ScanDLP) function can return where matches were found with `partid` option
- **`Imp`** Added [RCPT TO](http://docs.halon.se/hsl/rcptto.html) context `$tlsprotocol`, `$tlscipher` and `$tlskeysize` variables
- **`Imp`** Clear [HSL rate()](http://docs.halon.se/hsl/functions.html#rate)s based on a query (namespace and/or entry) over [SOAP](http://wiki.halon.se/SOAP) or web admin
- **`Imp`** Updated components
 - [CYREN](http://wiki.halon.io/CYREN) IP reputation (ctipd) and RPD (ctasd) engines
 - FreeBSD 10 [quarterly](http://pkg.freebsd.org/freebsd:10:x86:64/quarterly/) packages
 - FreeBSD [10.2-RELEASE-p9](https://www.freebsd.org/security/advisories/FreeBSD-SA-16:11.openssl.asc) fixing CVE-2015-3197 (SSLv2 disabled by default)
- **`Dep`** Removed the `system_default_quarantine` configuration key
- **`Dep`** Removed the `GetMailTransport()` function
- **`Dep`** Removed the [DeliverAsSpam()](http://wiki.halon.se/Deprecation#DeliverAsSpam) function
- **`Dep`** Deprecated the [WrapMessage()](http://wiki.halon.se/Deprecation#WrapMessage) function
- **`Dep`** Renamed the domain type `any` (catch-all) to the literal `*` in the configuration (converted)
- **`Dep`** Many default settings were moved to the user configuration (making them removable)

## 3.4-r3
Released on 2015-12-07
- **`New`** Added [anonymous functions](http://docs.halon.se/hsl/literals.html#function) and named function pointers
- **`New`** Added [array_filter()](http://docs.halon.se/hsl/functions.html#array_filter), array_map() and array_reduce() functions
- **`Imp`** The [in_file()](http://docs.halon.se/hsl/functions.html#in_file), [in_array()](http://docs.halon.se/hsl/functions.html#in_array) and [pcre_replace()](http://docs.halon.se/hsl/functions.html#pcre_replace) may take a function callback as argument
- **`New`** Added [csv_explode()](http://docs.halon.se/hsl/functions.html#csv_explode) function
- **`New`** `$serverip` in AUTH, RCPT TO and DATA context
- **`Imp`** Options `tls_protocols` and `tls_ciphers` added to [SetTLS()](http://docs.halon.se/hsl/predelivery.html#SetTLS) and smtp_lookup_\*
- **`Imp`** Reconnect without TLS if STARTTLS fails for optional TLS connections
- **`Imp`** SSLv3 disabled by default on outbound SMTP connections
- **`Imp`** Renamed DKIM function to [DKIMSign()](http://docs.halon.se/hsl/data.html#data.DKIMSign), which may return signature as a string
- **`New`** Added [csv_explode()](http://docs.halon.se/hsl/functions.html#csv_explode) function
- **`Imp`** [Deny()](http://docs.halon.se/hsl/api.html#Deny) in SOAP API may give a reason as faultstring
- **`Imp`** Improve logging in mailqueued (with queueid)
- **`Imp`** Setting `syslog_use_fqdn` which sends the FQDN in syslog messages
- **`Imp`** Overall elegance, design and usability improved
- **`Sec`** Updated FreeBSD to [10.2-RELEASE-p8](https://www.freebsd.org/security/advisories/FreeBSD-SA-15:26.openssl.asc) which fixes CVE-2015-3194 to 3196
- **`Bug`** Improved DNS reloading in HSL; affected the spf() and ldap_\*, tacplus_\* and radius_\* functions

## 3.4-r2
Released on 2015-11-04
- **`New`** [DANE](http://wiki.halon.io/DANE) support
- **`Imp`** Added settings page for [CYREN](http://wiki.halon.io/CYREN)
- **`Imp`** Added `extended_result` option to the [`dns*()`](http://docs.halon.se/hsl/functions.html#dns) functions
- **`Imp`** Added `pretty_print` option to [`json_encode()`](http://docs.halon.se/hsl/functions.html#json_encode)
- **`Imp`** Added `$receivedtime` to [pre](http://docs.halon.se/hsl/predelivery.html)- and [post](http://docs.halon.se/hsl/postdelivery.html)-delivery contexts
- **`Imp`** [SOAP](http://wiki.halon.io/SOAP) `mailQueue*Bulk()` functions returns number of affected messages
- **`Imp`** The default configuration now contains only one HTTPS web admin interface
- **`Imp`** Many small changes improving performance, stability, elegance, design and usability
- **`Bug`** Regression in `ScanRPD()` with `ctasd` for "valid-bulk"

## 3.4-r1
Released on 2015-10-19
- **`New`** [Sophos](https://www.sophos.com) anti-virus (`savdid`) engine
- **`New`** Spam classification [report](https://report.halon.se) buttons on email tracking page
- **`Imp`** Added [`explode()`](http://docs.halon.se/hsl/functions.html#explode) limit argument
- **`Imp`** Key size option when creating private keys on PKI page
- **`Imp`** Many small changes improving performance, stability, elegance, design and usability
- **`Bug`** Updated CYREN `ctasd` settings to better cope with connection errors
- **`Bug`** Updated Net-SNMP to fix memory leak in `snmpd`

## 3.4
Released on 2015-09-23
- **`New`** Based on [FreeBSD 10.2](https://www.freebsd.org/releases/10.2R/relnotes.html)
- **`New`** [SetTLS](http://docs.halon.se/hsl/predelivery.html#SetTLS) function to the pre-delivery context
- **`New`** [pie chart function](http://wiki.halon.se/Reporting#Functions) `q()` to graph queue/quarantine searches
- **`New`** Ability to disable services (such as. SNMP, FTP and SSH)
- **`New`** RCPT flow block for DNSBL and IP reputation
- **`Imp`** Zoomable graphs
- **`Imp`** Save graph layouts per user
- **`Imp`** Pie chart supports custom refresh intervals
- **`Imp`** Updated components
 - [CYREN](http://wiki.halon.io/CYREN) IP reputation (ctipd) and RPD (ctasd) engines
 - [Postfix 3](http://www.postfix.org/announcements.html), PostgreSQL 9.3.9 and ClamAV 0.98.7
- **`Imp`** Scripting page may easily run scripts from the (virtual text) file store
- **`Imp`** Optionally turn on `totalhits` in SOAP API
- **`Imp`** Switch between HTML and plain view in message preview
- **`Imp`** The AUTH rate limit flow block defer rather than reject when exceeded
- **`Imp`** Replaced `rpcmplexd` with an async web admin implementation
- **`Imp`** Overall performance, stability, elegance, design and usability improved
- **`Dep`** Updated OpenSSL requires DH key size of more than 512
- **`Dep`** Graphs now include "dots" in their names (previously replaced with a dash)
- **`Dep`** [SOAP API](http://wiki.halon.se/SOAP) changes
 - mailQueue's totalHits renamed to totalhits (lowercase)
 - Replaced loginFullname() and loginRemoteHost() with login() return object
 - Removed loginCheckPermission()
- **`Dep`** End user interface considerations
 - If you're using `display-stats` (graphs) you need to update the end user
 - Toggle preview on HTML/text message part is now supported

## 3.3-r6
Released on 2015-06-04
- **`New`** Added an "update" function to the [cache](http://docs.halon.se/hsl/structures.html#cache) that can pick expired (but valid) items
- **`New`** Added a `background` flag to the [http](http://docs.halon.se/hsl/functions.html#http) function for async, non-response calls
- **`New`** Added a [hash](http://docs.halon.se/hsl/functions.html#hash) function, useful together with <code>http()</code>'s background mode
- **`Imp`** Added a syslog port settings
- **`Imp`** Support implicit SSL (wrapper mode) by specifying "465" as the first listener port
- **`Imp`** Raised the free disk requirement to 1 GiB in order to receive new messages
- **`Bug`** Fix regression when enabling the DLP process `maildlpd` and viewing license users
- **`Bug`** Fixed augmented assignment (+=) behavior with function calls when dereferencing arrays
- **`Bug`** First run didn't add the second domain to the relay table
- **`Enduser`** If you use [end-user logging](https://wiki.halon.se/End-user#History_log), you may want to employ the new http background feature

## 3.3-r5
Released on 2015-05-11
- **`New`** Validate HSL scripts when saving a text file (in file store)
- **`New`** Added a <code>Defer()</code> function to the [AUTH](http://docs.halon.se/hsl/auth.html#Defer) flow
- **`Imp`** Automatically detect and support all network interfaces supported by FreeBSD
- **`Bug`** The [backend](http://wiki.halon.se/Backend) could crash when using LDAP in the [API (auth)](http://docs.halon.se/hsl/api.html) script
- **`Bug`** Regression in web admin causing some requests to fail due conservative settings
- **`Bug`** Adding new cluster nodes could fail if remote systems were unsorted (by id)
- **`Dep`** [SOAP](http://wiki.halon.se/SOAP) function `configValidateArgument` replaced with `hslCheckScript`

## 3.3-r4
Released on 2015-04-27
- **`Imp`** <code>return</code> statement in HSL without a value
- **`Bug`** `ESC` key in console may not work as expected if pressed twice rapidly
- **`Bug`** Temp disk may become full

## 3.3-r3
Released on 2015-04-22
- **`Imp`** Updated a lot of FreeBSD packages to quarterly
- **`Imp`** Support for Intel(R) 10Gb (ix) network adapters
- **`Bug`** SOAP request could be delayed with up to 1 second on idle systems
- **`Bug`** Adding too large text files in the File store now returns an error
- **`Dep`** switch statement in HSL with [explicit variable](http://wiki.halon.se/Deprecation#Switch_with_variable) storage

## 3.3-r2
Released on 2015-04-16
- **`New`** [dovecot_lookup_auth()](http://wiki.halon.se/HSL_core_functions#dovecot_lookup_auth) to authenticate using Dovecot's [authentication protocol](http://wiki.dovecot.org/Authentication%20Protocol)
- **`New`** [Done()](http://wiki.halon.se/HSL_DATA_context#Done) makes it easier to do [advanced routing](http://wiki.halon.se/LMTP)
- **`New`** [pcre_quote()](http://wiki.halon.se/HSL_core_functions#pcre_quote) makes it possible to use regex on user input
- **`New`** Preview on PKI page
- **`New`** Review &amp; save in plain-text editor
- **`Imp`** [http()](http://wiki.halon.se/HSL_core_functions#pcre_quote) function may skip SSL/TLS verification with ssl_verify_peer = false
- **`Imp`** Performance improvements in HSL's file handling
- **`Imp`** Updated third-party libraries
- **`Imp`** Easier to use CSV editor in web admin
- **`Imp`** Add support for keep-alive and gzip/deflate encoding in SOAP API
- **`Imp`** Support for QLogic NetXtreme II (bcm) network adapters
- **`Imp`** Fixed bug in "release duplicate" regarding delta files
- **`Imp`** Fixed bug with creating a cluster over HTTPS
- **`Dep`** [ScanSPF()](http://wiki.halon.se/Deprecation#ScanSPF) in favor of spf()
- **`Dep`** [ScanSARules()](http://wiki.halon.se/Deprecation#ScanSARules) in favor of ScanSA(["rules"=>true])
- **`Dep`** Quarantine profile's [trigger URL](http://wiki.halon.se/Deprecation#Trigger_URL)

## 3.3-r1
Released on 2015-03-02
- **`New`** VHD image runs on Microsoft Azure
- **`New`** DHCP addressing, default on Azure and GCE
- **`Imp`** Support [hardware-assisted software RAID](https://www.freebsd.org/doc/handbook/geom-graid.html) for many vendors such as Intel
- **`Imp`** Support for VirtIO (vtbd) and Xen (xbd) disks
- **`Imp`** Support for Intel 10Gb (igb) network adapters
- **`Imp`** Ctrl+A/E in web terminal
- **`Bug`** Fixed regressions in web admin

## 3.3
Released on 2015-02-16
- **`New`** Updated to [FreeBSD 10.1](https://www.freebsd.org/releases/10.1R/announce.html)
- **`New`** Added [transparent proxy](http://wiki.halon.se/Proxy) features
 - The `system_nonlocal_source` setting enables [`SetSourceIP()`](http://wiki.halon.se/HSL_Mail_Queue#SetSourceIP) to spoof source IPs
 - XCLIENT support for [external proxies](http://wiki.halon.se/Proxy#Fully_transparent_mode)
- **`New`** Added new features to the scripting language (HSL)
 - [`SetMetaData()`](http://wiki.halon.se/HSL_DATA_context#SetMetaData) and [`GetMetaData()`](http://wiki.halon.se/HSL_Mail_Queue#GetMetaData) to pass data between DATA and queue scripts
 - [`syslog()`](http://wiki.halon.se/HSL_core_functions#syslog) function
 - [`unset()`](http://wiki.halon.se/HSL_core_functions#unset) statement
 - `SetRecipient()` in pre-delivery script
 - `$senderhelo` in pre-delivery script
 - `$transfertime` in post-delivery script
 - `$saslusername` in queue (pre- and post-delivery) script
 - [Raw strings](http://wiki.halon.se/HSL_variables_and_data_types#Raw_strings), like ''raw string''
 - Allow `globalview()` and `dnsbl()` to be executed from `hsh`
- **`New`** Extended [search filters](http://wiki.halon.se/Search_filter) (HQL) syntax
 - `metadata.field=` corresponding to `SetMetaData()`
 - `size=` (message body)
 - `helo=` (HELO/EHLO hostname)
- **`Imp`** Web admin interface
 - Refreshed with many improvements (in layout and functionality)
 - The icons and images are vectorized (to support retina/HiDPI displays)
 - Button to reset (RRD) graphs
 - Custom score popup for Internet Explorer (which allows spam scores and refid to be copied)
- **`Imp`** Added "msgsize" and "msghelo" to [SOAP](http://wiki.halon.se/SOAP) API
- **`Imp`** SMTP balancing uses uniform distribution of traffic
- **`Imp`** Support for QLogic 10Gb (bxe) network adapters
- **`Imp`** Searching text logs is a lot faster
- **`Imp`** `mail_queue_threads` may now be raised
- **`Imp`** Updated 3rd-party components such as CYREN (8.0.110) and Kaspersky (3.8.0.4)
- **`Dep`** Built-in `batv_*()` is removed, use the [HSL implementation ](http://wik.halon.se/BATV)
- **`Dep`** Renamed "gmt0" to "utc" in SOAP API
- **`Dep`** `$recipientdomains` and `$recipients` in DATA context are now read-only
- **`Dep`** [`http()`](http://wiki.halon.se/HSL_core_functions#http) return empty results on non 2** responses
- **`Dep`** `GetAddressList()` returns empty list on parse errors instead of throwing an exception
- **`Dep`** Web admin's flow block "Add header" appends a new header instead of using `SetHeader()`
- **`Dep`** `GetID()` is now removed, was deprecated in 3.0
- **`Dep`** `$directprocessing` is now removed, was deprecated in 3.2

## 3.2-r10p1
Released on 2014-12-23
- **`Bug`** Stability fixes in `mailscand`
- **`Bug`** Fixes regression that caused some admin and `clusterd` requests to fail

## 3.2-r10
Released on 2014-11-17
- **`Imp`** [SetSender()](http://wiki.halon.se/HSL_Mail_Queue#SetSender) in pre-delivery (queue) script
- **`Imp`** LSI MegaRAID tool ([mfiutil](https://www.freebsd.org/cgi/man.cgi?query=mfiutil)) available
- **`Imp`** hslCacheClear() [SOAP API](http://wiki.halon.se/SOAP) may clear a specific namespace/function
- **`Imp`** Added [SOAP API](http://wiki.halon.se/SOAP) mailQueueRetryBulk() function
- **`Imp`** Added 'duplicate' option to [SOAP](http://wiki.halon.se/SOAP)'s queue function for cloning messages(s) from an [archive](http://wiki.halon.se/Archiving)
- **`Imp`** Setting mail_log_size to zero will disable logging (even realtime)
- **`Imp`** Disable SSLv2 and SSLv3 on administration UI (and SOAP)
- **`Imp`** Add custom headers to HSL [mail()](http://wiki.halon.se/HSL_core_functions#mail) created messages
- **`Imp`** [pcre_replace()](http://wiki.halon.se/HSL_core_functions#pcre_replace) HSL function
- **`Imp`** [Variable substitution](http://wiki.halon.se/HSL_variables_and_data_types#Variable_interpolation) with ${name}
- **`Bug`** 'Next retry' could be presented with the wrong timezone (didn't affect delivery)
- **`Bug`** Memory usage could show erroneous on 64 bit platforms
- **`Dep`** SOAP API mailQueueRetryAll() removed (reimplemented with mailQueueRetryBulk)
- **`Dep`** SOAP API devList() removed

## 3.2-r9
Released on 2014-10-01
- **`New`** Added [LMTP](http://en.wikipedia.org/wiki/Local_Mail_Transfer_Protocol) support, useful for more efficient [Dovecot](http://wiki2.dovecot.org/LMTP) delivery
- **`Imp`** retry=x in [search filter](http://wiki.halon.se/Search_filter), useful to show [delayed](http://wiki.halon.se/HSL_Mail_Content#SetDelayedDeliver) [messages](http://wiki.halon.se/HSL_Mail_Queue#Reschedule)
- **`Imp`** Added "\r\n\t" syntax in HSL strings
- **`Imp`** Added HSL http() max-time timeout, also renamed connect_timeout
- **`Imp`** Added the [SMTP ping](https://github.com/halonsecurity/smtpping) command
- **`Imp`** Decouple antivird and clamd for more efficient RAM utilisation
- **`Imp`** New installations are 64-bit, with VMware "guest OS" set to "freebsd-64"
- **`Imp`** Review before save on virtual text files and DLP pages
- **`Imp`** New certificates are generated with SHA256
- **`Imp`** Faster clearing of rate limits (may interrupt garbage collection)
- **`Imp`** Faster connect() timeout in smtp_lookup_rcpt()
- **`Imp`** Lower connect() timeout to 30s (like Postfix)
- **`Bug`** Problem when searching rates in web user interface
- **`Dep`** Undefined values in HSL was branched as true (not false)

## 3.2-r8
Released on 2014-09-11
- **`Sec`** Updated to FreeBSD 10.0-RELEASE-p8 which addresses new [OpenSSL](https://www.freebsd.org/security/advisories/FreeBSD-SA-14:18.openssl.asc) bugs
- **`New`** Multiple "shadow" port support for mail listener, for better pool utilisation
- **`New`** Added `SetHELO()` function and `$sourceip` to [pre-delivery script](http://wiki.halon.se/HSL_Mail_Queue)
- **`Imp`** Global HSL variables are committed when calling a second function
- **`Imp`** New chart for swap operations, as complement to swap usage chart
- **`Imp`** Updated Kaspersky anti-virus engine to 8.3
- **`Imp`** Some search queries are maintained when browsing cluster nodes
- **`Imp`** Many 64-bit fixes in preparation for upcoming 64-bit release
- **`Imp`** Display Kaspersky virus base version in log on startup
- **`Bug`** Rate limit page support any valid UTF8 as namespace and entry
- **`Imp`** Overall improvements throughout the system
- **`Bug`** Fixes NTP client regression
- **`Bug`** Fixes VMware guest info regression
- **`Bug`** Link aggregation fixes; omitted from cluster, and brings up all ports
- **`Bug`** Fixed cluster system update page's node link
- **`Bug`** Fixed cluster configuration override page with multiple fields per key
- **`Dep`** Forbids ambiguous HSL concatenation of numbers

## 3.2-r7
Released on 2014-08-20
- **`New`** Implemented a [pre-delivery (queue)](http://wiki.halon.se/HSL_Mail_Queue) script for dynamic transport behaviour
- **`New`** Added the [log()](http://wiki.halon.se/HSL_core_functions#log) function which can be used for things such as [GeoIP](http://wiki.halon.se/HSL_code_examples#GeoIP) lookup
- **`New`** Added the [timelocal()](http://wiki.halon.se/HSL_core_functions#timelocal) function to get time in local time
- **`New`** [Link aggregation](http://www.freebsd.org/cgi/man.cgi?query=lagg&amp;apropos=0&amp;sektion=0&amp;manpath=FreeBSD+10.0-RELEASE&amp;arch=default&amp;format=html) support
- **`Imp`** Support using system disk as [storage](http://wiki.halon.se/Architecture#Disk_layout) on bare-metal installs, or if the virtual disk is grown
- **`Imp`** The [post-delivery (transport)](http://wiki.halon.se/HSL_Mail_Transport) script is unified for all transport, on the flow page
- **`Imp`** The [GetHeaders()](http://wiki.halon.se/HSL_Mail_Content#GetHeaders) function can be used to fetch all headers as a multidimensional array
- **`Imp`** Allow multiple [include](http://wiki.halon.se/HSL_control_structures#include) of same file in HSL
- **`Imp`** The [post-delivery (transport)](http://wiki.halon.se/HSL_Mail_Transport) script executed for successful deliveries, useful for external logging
- **`Imp`** Added `$actionid` variable to DATA, queue and transport flows, for tracking of recipients, etc between flows
- **`Imp`** Loopback addresses configuration, useful for DSR load balancing
- **`Imp`** Change VLAN and link aggr. settings from console
- **`Imp`** Updated FreeBSD packages to latest quarterly
- **`Imp`** Auto-configuration on Google Compute Engine
- **`Imp`** Many minor improvements
- **`Bug`** Changed SpamAssassin queue algorithm to decrease wait time
- **`Bug`** Issue when searching logs larger than 2 GiB fixed
- **`Bug`** Issue where Kaspersky wrote files to /tmp fixed
- **`Dep`** Disabled [Bayesian](http://wiki.halon.se/SpamAssassin) by default

## 3.2-r6p1
Released on 2014-06-18
- **`Bug`** Resolved uncommon stability issue

## 3.2-r6
Released on 2014-06-10
- **`Sec`** Fix [OpenSSL CVE-2014-0195](http://www.freebsd.org/security/advisories/FreeBSD-SA-14:14.openssl.asc), 2014-0221, 2014-0224 and 2014-3470
- **`New`** [DiscardMailDataChanges()](http://wiki.halon.se/HSL_DATA_context#DiscardMailDataChanges) function, allowing different data changes for different CopyMail()s
- **`New`** Support for [variadic function](http://wiki.halon.se/HSL_control_structures#Variadic_functions) syntax in HSL
- **`New`** Added [spread operator](http://wiki.halon.se/HSL_control_structures#Argument_unpacking) (argument unpacking) to HSL
- **`Imp`** Added executable file (by file name, even in ZIP and other archives) blocking to antivirus block
- **`Imp`** Performance improvements in [ScanDLP](http://wiki.halon.se/HSL_Mail_Content#ScanDLP) for efficient file extension scanning
- **`Imp`** Encode headers as quoted-printable instead of Base64 for readability
- **`Imp`** View ScanRPDAV (VOD) results in web admin's message tracking
- **`Imp`** Improved virtual text file editor, with [HSL code](http://wiki.halon.se/HSL) support (great for [includes](http://wiki.halon.se/HSL_control_structures#include))
- **`Imp`** Removed deprecated browser-specific CSS3 options (Mozilla, Opera)
- **`Imp`** Enable auto-scroll on keypress in web terminal
- **`Imp`** Many minor improvements

## 3.2-r5
Released on 2014-05-23
- **`New`** Added [SetDelayedDeliver()](http://wiki.halon.se/HSL_Mail_Content#SetDelayedDeliver) function to [HSL](http://wiki.halon.se/HSL) for extra queueing time before delivery
- **`New`** Added [builtin](http://wiki.halon.se/HSL_control_structures#builtin) and [global](http://wiki.halon.se/HSL_control_structures#global) control structures to [HSL](http://wiki.halon.se/HSL) functions
- **`New`** Added [json_encode()](http://wiki.halon.se/HSL_core_functions#json_encode) function to [HSL](http://wiki.halon.se/HSL)
- **`Imp`** Added max depth option [HSL](http://wiki.halon.se/HSL)'s [ScanDLP()](http://wiki.halon.se/HSL_Mail_Content#ScanDLP), useful for file extension matching in archives, eg.
- **`Imp`** Added named match groups to [HSL](http://wiki.halon.se/HSL)'s [PCRE](http://wiki.halon.se/HSL_core_functions#pcre_match) functions
- **`Imp`** Adding filtering on retry and sender field to [HSL](http://wiki.halon.se/HSL)'s [GetMailQueueMetric](http://wiki.halon.se/HSL_Mail_Content#GetMailQueueMetric) function
- **`Imp`** Updated SpamAssassin to 3.4.0
- **`Imp`** Web terminal (command page) support pasting with Ctrl+V
- **`Imp`** Always prefer IPv6 when clustering with hostnames
- **`Imp`** Support RFC 2231 header parsing
- **`Imp`** Various web admin enhancements, such as links from quarantine page to tracking
- **`Imp`** Overall performance and reliability improved
- **`Bug`** Resolved issue where adding and removing headers with zero offset conflicted

## 3.2-r4
Released on 2014-04-28
- **`Dep`** Deprecated updateNetwork SOAP API function
- **`Dep`** Deprecated HSL's null coalescing operator
- **`New`** Added [default function arguments](http://wiki.halon.se/HSL_control_structures#Default_arguments) in HSL
- **`Imp`** HSL's [header functions](http://wiki.halon.se/HSL_Mail_Content#Message_header_functions) decode and refold by default
- **`Imp`** Added `msgqueueid` to mailHistory [API](http://wiki.halon.se/SOAP) and `historyid` [search filter](http://wiki.halon.se/Search_filter)
- **`Imp`** Overall performance and stability improved
- **`Bug`** HSL's `per_message` [cache](http://wiki.halon.se/HSL_control_structures#cache) now works in functions
- **`Bug`** Pressing back button in Firefox no longer reset forms

## 3.2-r3
Released on 2014-04-08
- **`Sec`** Patched OpenSSL ["heartbleed"](http://heartbleed.com) vulnerability (CVE-2014-0160)
- **`Dep`** Deprecated BATV functions in favor of [HSL implementation](http://wiki.halon.se/BATV#Implementation)
- **`New`** Introduced [array slicing](http://wiki.halon.se/HSL_variables_and_data_types#Slicing) to HSL
- **`Imp`** HSL's [DeliverWithDKIM()](http://wiki.halon.se/HSL_Mail_Content#DeliverWithDKIM) function can load private key from variable, such as [http()](http://wiki.halon.se/HSL_core_functions#http) request
- **`Imp`** New HSL variable $tlsstarted in AUTH and [RCPT flow](http://wiki.halon.se/HSL_Mail_Recipient)
- **`Imp`** New HSL variables $messageid and $queueid in [transport flow](http://wiki.halon.se/HSL_Mail_Transport#Pre-defined_variables)
- **`Imp`** Message queue IDs (exposed as $queueid or via SOAP API) upgraded to 64-bit integer
- **`Imp`** Improved [http()](http://wiki.halon.se/HSL_core_functions#http)'s POST data serialisation and added "response_headers" option
- **`Imp`** Added a [gethostname()](http://wiki.halon.se/HSL_core_functions#gethostname) function to HSL
- **`Imp`** Many performance optimisations in HSL
- **`Bug`** Fixed Firefox quirk with forms resetting when going back on page
- **`Bug`** HSL's dnstxt() concatenate multiple strings with space
- **`Bug`** Clustered line charts now merge new legends from secondary results
- **`Bug`** Display error message if unable to clear cluster's HSL cache

## 3.2-r2
Released on 2014-03-10
- **`New`** Extended the [HSL scripting](http://wiki.halon.se/HSL) language
 - [GetMailQueueMetric()](http://wiki.halon.se/HSL_DATA_context#GetMailQueueMetric) to implement usage quotas in queues
 - [json_decode()](http://wiki.halon.se/HSL_core_functions#json_decode), is_string() and is_number() for making API calls, etc
 - [http()](http://wiki.halon.se/HSL_core_functions#http) function now supports custom request method and headers
 - %= and **= operators
 - Switch statements validates that a switch is directly followed by a case or default label
- **`Imp`** Updated [SOAP API](http://wiki.halon.se/SOAP)
 - configKeys() now takes "key" (filter) argument which is also exported in $soapargs[]
 - configKeySet() allows partial updates (not all parameters needs to be specified)
 - hslRate() and hslRateClear() exports "ns" and "entry" to $soapargs[]
 - hslRate() and statList() now implements pagination and backend-side search/filtering
 - mailQueue() and mailHistory() includes msgsasl for username and msgts0 for GMT timestamp
 - mailQueue() and mailHistory() supports filtering on sasl=
- **`Imp`** SASL username can be viewed on tracking page
- **`Imp`** DSN messages now include original header "Undeliverable: This was the original header"
- **`Imp`** Support for Broadcom's [bge](http://www.freebsd.org/cgi/man.cgi?query=bge) NICs
- **`Bug`** Web admin interface fixes
 - Netcat (nc) command with custom port was not correctly documented
 - Active HTTPS sessions may not be degraded to HTTP
 - The authentication script test sandbox could produce the wrong output
 - Some quarantine retention policies were kept for too long, affected users need to reselect their intended policy

## 3.2-p1
Released on 2014-02-12
- **`Bug`** Xen PVHVM network driver "xn" was not detected properly
- **`Bug`** The command API could return empty results under extremely rare circumstances
- **`Bug`** The web admin's hardware page didn't list "ada" devices

## 3.2
Released on 2014-02-10
- **`New`** Hyper-V para-virtualization; gigabit network, VLANs, SCSI disks, etc
- **`New`** Virtio (KVM) para-virtualization; improved network and disk performance
- **`New`** VMware VMXNET3 support
- **`New`** Xen PVHVM support
- **`New`** Line graphs showing disk IOPS and latency
- **`New`** Show message modifications when browsing queued or quarantined messages
- **`New`** The [DATA flow registers](http://wiki.halon.se/HSL_DATA_context#Pre-defined_variables) `$recipients` and `$recipentdomains`
- **`New`** New HSL function [`abs()`](http://wiki.halon.se/HSL_core_functions#abs)
- **`New`** Added [`tcpdump`](http://www.freebsd.org/cgi/man.cgi?query=tcpdump) to API and web administration
- **`Imp`** Based on [FreeBSD 10](https://www.freebsd.org/releases/10.0R/announce.html) and compiled with clang
- **`Imp`** LDNS and Unbound as replacement for BIND (as resolver and DNS cache)
- **`Imp`** Automatically grow storage disk when resized in hypervisor
- **`Imp`** Overall throughput increased by careful profiling
- **`Imp`** Large number of HSL scripting language optimisations, such as
 - R-value optimisations
 - Made `str_replace()` significantly faster
 - Optimised [augmented assignments](http://wiki.halon.se/HSL_operators#Augmented_assignment_operators)
 - Pre-compiled [regular expressions](http://wiki.halon.se/HSL_variables_and_data_types#Regular_expressions)
- **`Imp`** More concise and helpful logging throughout the system
- **`Imp`** Increased swap partition size to 2 GB
- **`Imp`** Updated all 3rd-party components
- **`Imp`** Show warnings if no storage disk is found or configured
- **`Imp`** Rebrand Commtouch as [CYREN](http://www.cyren.com)
- **`Imp`** Enable some [SpamAssassin](http://wiki.halon.se/SpamAssassin) DNSBLs by default
- **`Imp`** Cache DKIM signature for all recipients
- **`Imp`** Overall improvements
- **`Bug`** DKIM DNS generator lacked `_domainkey` part
- **`Bug`** Under certain circumstances, the command API could fail
- **`Bug`** Reload flows when file store objects are changed
- **`Bug`** Fixed issue with pre-boot command line shutdown
- **`Dep`** Deprecated the second argument to HSL's `round()` function
- **`Dep`** Deprecated the DATA flow's `$result` and `$directprocessing` predefined variables
- **`Dep`** New (S)ATA storage disks are identified as "ada" instead of "ad"
- **`Dep`** At least one DNS server is necessary; unbound is not configured to traverse from the DNS root

## 3.1-r4p1
Released on 2014-01-16
- **`Bug`** Prevent NTP [reflection attacks](http://www.freebsd.org/security/advisories/FreeBSD-SA-14:02.ntpd.asc)

## 3.1-r4
Released on 2013-12-20
- **`Imp`** Refactoring for performance improvements
- **`Imp`** Warn about 32-bit hosts as preparation for 64-bit releases
- **`Imp`** Estimates the number of mail tracking search results
- **`Imp`** Changed various settings from byte to megabyte
- **`Imp`** Overall web administration improvements
- **`Bug`** Unable to add cluster nodes with literal IPv6
- **`Bug`** Regression on graph page's rate counter

## 3.1-p3
Released on 2013-11-21
- **`New`** [Clustered](http://www.halon.se/blogs/centralised-and-cluster-synchronised-rate-limiting/) `rated` process for improved [rate limiting](http://wiki.halon.se/Rate_limiting)
- **`New`** [GetAddressList()](http://wiki.halon.se/HSL_DATA_context#GetAddressList) function in DATA flow
- **`New`** [is_subdomain()](http://wiki.halon.se/HSL_core_functions#is_subdomain) HSL function
- **`Imp`** Support sub-domains i black/whitelists (.example.com)
- **`Imp`** Search for transports on tracking page
- **`Imp`** Web admin terminals now work in background tabs
- **`Imp`** IPv6 cluster support
- **`Imp`** Always give a authentication failure reason in `mailpolicyd`
- **`Bug`** Catch exception in video console for systems without serial number
- **`Bug`** Do not create sessions for unauthorized web admin clients

## 3.1-p2
Released on 2013-10-29
- **`Imp`** Improved mail queue/quarantine delivery performance
- **`Imp`** Significantly improved mail tracking performance
- **`Imp`** Support for more than two NTP servers
- **`Imp`** Returns to current page, when fixing TLS fingerprints
- **`Imp`** Warns about [Cisco SMTP fixup](http://wiki.halon.se/FAQ#Cisco_SMTP_fixup_problems) which is known to cause issues
- **`Imp`** Shows inode usage on storage/hardware page
- **`Imp`** Other minor improvements
- **`Bug`** Detect scrolling more accurately when viewing logs
- **`Bug`** Windows users couldn't type @ in the terminal

## 3.1-p1
Released on 2013-10-10
- **`Imp`** Improved Bayesian performance using SDBM database
- **`Imp`** Cluster overview page shows new software versions
- **`Bug`** Regression causing issues for users with ATA write cache enabled

## 3.1
Released on 2013-10-09
- **`New`** Based on FreeBSD 9.2
- **`New`** Support for KVM VirtIO networking
- **`New`** Create pie graph from [rate()](http://wiki.halon.se/HSL_core_functions#rate) information [with r()](http://wiki.halon.se/Reporting)
- **`New`** Buy licenses directly from within product
- **`Imp`** Improved rate control page (with thresholds)
- **`Imp`** DLP engine inspects more archive formats
- **`Imp`** Download messages as ZIP instead of tar
- **`Imp`** Restructured menu layout
- **`Imp`** Script editor behaviour in Firefox and Internet Explorer
- **`Imp`** Overall performance improvements

## 3.0-p9
Released on 2013-09-23
- **`Imp`** Better user experience for Hyper-V deployments
- **`Imp`** Pages loads faster thanks to GZIP compression
- **`Imp`** Overall performance improvements
- **`Bug`** Rebooting was required to effectuate some license changes

## 3.0-p8
Released on 2013-09-09
- **`New`** DMARC flow block and [ScanDMARC](http://wiki.halon.se/HSL_DATA_context#ScanDMARC) function
- **`Imp`** Convert white/blacklist input to lower case
- **`Imp`** Optimized history/mail API (database API)
- **`Imp`** Optimized message logs extractions (from 4 minutes to ~0 seconds)
- **`Imp`** Improved charset detection (ICU)
- **`Imp`** Improved escape sequence in VMware terminal (detach keyboard)
- **`Imp`** [Search](http://wiki.halon.se/Search_filter) for scores and RPD ID in tracking
- **`Imp`** Improved SPF caching
- **`Imp`** Updated Ace editor and Kaspersky anti-virus engine
- **`Bug`** IE9 had problems with search on tracking page
- **`Bug`** Searchlog didn't always find message logs (if incomplete log)
- **`Bug`** 7-zip couldn't open downloaded tar (message) archives
- **`Bug`** Paging with a quarantine folder selected

## 3.0-p7
Released on 2013-08-12
- **`Imp`** SMTP client prefers "strongest" SASL method announced by server
- **`Bug`** Memory leak in the console UI

## 3.0-p6
Released on 2013-08-09
- **`Bug`** Initial vApp configuration imported multiple times
- **`Bug`** XML warning on non-VMware system's interface page

## 3.0-p5
Released on 2013-08-07
- **`New`** Network setup guide in OVF (VMware vCenter)
- **`Imp`** Create cluster with optional TLS
- **`Imp`** Test end-user API with from scripting page
- **`Imp`** Added an extra certificate (pki:2) for SMTP
- **`Imp`** http() support HTTPS
- **`Bug`** Clustering with SSL certificate chains

## 3.0-p4
Released on 2013-07-24
- **`New`** Black/whitelist module for end-user interface
- **`Imp`** Full-text search in subject lines
- **`Imp`** Clear search query on tracking page
- **`Imp`** Return to referring page when editing profiles, etc
- **`Imp`** Export users per domain on license page
- **`Imp`** Prefer outbound CRAM-MD5 authentication method if supported
- **`Bug`** BATV interoperability improvements

## 3.0-p3
Released on 2013-07-05
- **`Imp`** Search filters are now case-insensitive for from/to/ip
- **`Imp`** Blacklist module in RCPT TO flow
- **`Imp`** Dragging/selecting an interval in a graph opens tracking
- **`Imp`** Various improvements to the DLP engine
- **`Imp`** Filter commandRun and fileRead arguments in authentication script
- **`Imp`** Compare IP addresses with in_network() in white/blacklists blocks
- **`Imp`** Discard mailqueue's pre-fetched work queue when deleting messages

## 3.0-p2
Released on 2013-06-25
- **`New`** [Complete overhaul](https://halon.io/blog/sneak-peek-of-the-email-gateway-sp-version-3-0/) of the product
- **`Imp`** The [SOAP API](http://wiki.halon.se/SOAP) is completely changed
- **`Imp`** [SNMP MIB](http://wiki.halon.se/SNMP) is completely changed
- **`Dep`** [Quarantine](http://wiki.halon.se/Quarantine) is deprecated; moved from the system to a [GitHub project](https://github.com/halonsecurity/sp-enduser)

## 2.4.0.3
Released on 2013-02-21
- **`Imp`** Microsoft Hyper-V legacy network driver support
- **`Bug`** Some freshclam still couldn't download daily updates

## 2.4.0.2
Released on 2013-02-18
- **`Bug`** ScanSA() could miscalculate the estimated queue wait time
- **`Bug`** Workaround for freshclam failing to update since ClamAV didn't create a daily diff

## 2.4.0.1
Released on 2012-10-15
- **`Imp`** Overall improvements
- **`Bug`** Resolved bug in recipient flow's blacklist module's script generation
- **`Bug`** Resolved statistics bug that could create spikes during database failures
- **`Bug`** Resolved database issues generating warnings under rare circumstances
- **`Bug`** Cluster overview's reporting could fail to load

## 2.4
Released on 2012-10-09
- **`New`** Based on FreeBSD 9
- **`New`** ScanSA() got fair queueing, time estimation, size limit, etc
- **`New`** Boot-time management via bootsysmgr
- **`New`** TTL argument to IP Policy's Allow() and Block()
- **`Imp`** Improved performance
- **`Imp`** Improved watchdog with better logging
- **`Imp`** Save RAM by only starting maildlpd if ScanDLP() is used
- **`Imp`** In case of storage disk problems, boot without storage
- **`Imp`** Allow messages to be viewed instead of downloaded in quarantine
- **`Imp`** GetDSN() and GetDSNHeader() to support text/rfc822-headers
- **`Imp`** DNS shuffling based on MessageID (always the same per message)
- **`Imp`** Reboot/shutdown is significantly faster
- **`Bug`** Missing {FOOTER} replacement in WrapMessage
- **`Dep`** The following SOAP API's has been removed:
 - System_Reboot_Hard
 - System_Shutdown_Hard
 - System_Online_Status
 - Management_SetStorageRecover
 - Management_StorageRecoverStatus
 - Management_SetStorageMigrate
 - Mail_Domain_Report
 - Config_Diff
 - System_GetKey("system_config_revision")
 - System_Command_Run_XXX (replaced with by System_Command_Run)
 - Management_GetArguments' filter parameter

## 2.3.6.3
Released on 2012-09-07
- **`Bug`** Regression in `backend`'s SOAP server

## 2.3.6.2
Released on 2012-09-04
- **`New`** Deliver to an MX of a hostname using lookup-mx:hostname
- **`Imp`** Configuration diff is coloured in red and green
- **`Imp`** SPF module is moved to content flow in default configuration
- **`Imp`** SOAP API's WSDL file moved to /remote/?wsdl
- **`Imp`** SOAP API deprecated key system_config_revision, use GetHistoryEntries
- **`Imp`** SOAP API deprecated Config_Diff
- **`Imp`** SOAP API's gSOAP updated
- **`Imp`** Disallow saving a configuration with no changes
- **`Imp`** Web administration checkbox labels made clickable
- **`Imp`** backend's watchdog report error codes
- **`Bug`** SPF couldn't verify IPv6 senders
- **`Bug`** The configuration partition wasn't checked properly
- **`Bug`** Monotonic time was not used for all timers
- **`Bug`** Visual bugs in web administration resolved

## 2.3.6.1
Released on 2012-07-18
- **`Bug`** Fixes various spam assassin errors
- **`Bug`** Fixes clustering page when clustering is not configured

## 2.3.6
Released on 2012-07-04
- **`New`** Introduces pattern analysis rules from Halon
- **`New`** Introduces valid bulk (RPD score 40) for non-spam
- **`Imp`** Rate limits now summarized in cluster
- **`Imp`** Display of rate limits and licensed users loads faster
- **`Imp`** Table elements' full content shown on mouse over
- **`Imp`** Improved cluster navigation behavior
- **`Imp`** Updated 3rd-party libraries
- **`Imp`** Faster spam-assassin updates
- **`Imp`** Faster rendering of log files
- **`Bug`** IP policy charts was not available on overview page
- **`Bug`** Spam assassin error (introduces in previous release)
- **`Bug`** Fixed MIME-decoding in quarantine

## 2.3.5
Released on 2012-06-08
- **`New`** French translations
- **`Imp`** Pattern analysis' (SA's) score values are reported in Tracking/History
- **`Imp`** HSL's [`ScanSARules()`](http://wiki.halon.se/SP/HSL_Mail_Content#ScanSARules.28.24options.29) can return score values
- **`Imp`** HSL's [`Quarantine()`](http://wiki.halon.se/SP/HSL_Mail_Content#Quarantine.28.24quarantinepolicy.2C_.24recipient.2C_.24transportid.2C_.24options.29) has new reject and final action options
- **`Bug`** Issue with HSL's `Quarantine()` $recipient resolved

## 2.3.4.1
Released on 2012-05-08
- **`New`** Added `tcpdump` to CLI's Network > Diagnostic Tools (console/SSH)
- **`Imp`** Commtouch reference IDs in web administration
- **`Imp`** HSL's `ScanRPD()` can return reference ID
- **`Imp`** Added server= and transport= to the Tracking's [search filters](http://wiki.halon.se/SP/Search_filter)
- **`Imp`** HSL [`pcre_match`](http://wiki.halon.se/SP/HSL_core_functions#pcre_match.28.24pattern.2C_.24input.29) improved, empty capture groups, etc.
- **`Bug`** Web administration spelling

## 2.3.4
Released on 2012-03-22
- **`New`** Mail tracking supports [boolean search filters](http://wiki.halon.se/SP/Search_filter)
- **`New`** Mail tracking integrates history and queue
- **`New`** HSL [pcre_match](http://wiki.halon.se/SP/HSL_core_functions#pcre_match.28.24pattern.2C_.24input.29) functions
- **`New`** HSL Mail Content [GetHeaders](http://wiki.halon.se/SP/HSL_Mail_Content#GetHeaders.28.24header.2C_.24wordencode_.3D_true.29) function
- **`Imp`** Cluster mail tracking displays scores, and more
- **`Imp`** Jump between message tracking and logging seamlessly
- **`Imp`** Jump between pages/tabs before loading completes
- **`Bug`** Issue with DSNs/NDRs displaying in Microsoft OWA resolved
- **`Bug`** Issue with UDP when ARP tables changes resolved
- **`Bug`** Web administration diagnostics issue resolved

## 2.3.3
Released on 2012-02-23
- **`Imp`** Multi-line reject/defer messages
- **`Imp`** Updated 3d-party modules (ctipd, ctengine, postfix, clamav, openldap)
- **`Imp`** Added user defined callback to cache[], using "ttl_function" argument
- **`Imp`** Include SMTP transaction state in SMTP errors
- **`Imp`** Support for CA in LDAPs
- **`Bug`** Web admin could visually overflow if too many remote systems
- **`Bug`** Resolved rare bug with anti-virus engine
- **`Bug`** Fix TLS warning on startup
- **`Bug`** Verify last fingerprint in SSL chain (consistently)
- **`Bug`** Scripting console could not connect to SMTP servers over TLS
- **`Bug`** Resolved issue with HSL construct barrier {}
- **`Bug`** SMTP lookup recipient could cache entires for too long

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
- **`Dep`** Configuration key config_user renamed to to system_user
- **`Dep`** Signed in account used to browse cluster in web admin
- **`Dep`** Admin accounts must use @local for quarantine sign-in

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
- **`Bug`** Flow selection race condition for first message resolved
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
- **`Dep`** It's recommended to empty your browser cache before signing on to your updated system
- **`Dep`** The log format is heavily changed; be aware if you rely on machine parsed logging

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
- **`Bug`** Trace configuration revisions changes by administrator user
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
- **`Imp`** Script testing tool
- **`Imp`** Searching logs indicates when showing realtime
- **`Imp`** Custom icons for script blocks in Web Admin
- **`Imp`** Improved anti-virus detection
- **`Imp`** SOAP interface improvements
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
