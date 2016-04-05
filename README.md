New systems are deployed by [downloading](http://dl.halon.se/vsp/) a disk image or virtual machine template. Existing systems are updated by simply pressing the automatic update button on the system's update page.

There is an [RSS feed](https://github.com/halonsecurity/changelog/releases.atom) available.

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
