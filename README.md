New systems are deployed by [downloading](http://dl.halon.se/vsp/) a disk image or virtual machine template. Existing systems are updated by simply pressing the automatic update button on the system's update page.

There is an [RSS feed](https://github.com/halonsecurity/changelog/releases.atom) available.

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
