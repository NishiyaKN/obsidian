### ICT Skills and Working in Linux
- Applications requests resources (disk, RAM, etc) to the kernel throught the kernel API
- Process is an abstraction of a single task loaded and tracked by the kernel. An app may need multiple processes
### Major Open Source Applications
##### Server Aplications
- Web server applications: Apache HTTPD, NGINX
- Private cloud applications: ownCloud, Nextcloud
- Database aplications: MariaDB, PostgreSQL, Firebird
- Email server applications:
	- MTA (transfer emails): Sendmail, Postfix
	- MDA (stores emails in the user mailbox): invoked from the final MTA in the chain
	- POP/IMAP server (communication protocol between client and server): Dovecot, Cyrus IMAP
- File sharing: 
	- Samba: makes Linux machine look like and behave as a Windows machine
	- Netatalk: same as Samba, but for Apple Macintosh file server. 
	- NFS: Network File System, native file sharing protol for UNIX, a remote file system can be mounted like a regular disk
	- OpenLDAP: Lightweight Directory Access Protocol, used to manage and access a directory of information over a network. (A directory is basically a database in binary tree format that can be used to authenticate users)
### Package management
- According to the Linux Foundation, ==RPM== is the standard package management system
- RPM is used by RHEL, SUSE, Arch, etc.
- Yumex, Gnome PackageKit -> GUI for rpm management

### Security
- Linux sysadmins will usually disable root access

### License
**Copyleft Licenses**:  Any derivative software must be released under the same license terms, preserving the open sourceness
- **GPLv2** - Used by the Linux kernel. If you modify the kernel, you must share the modifications.
- **GPLv3** - Created by RS to avoid tivoization. You can't use proprietary hardware that blocks the usage of modified software. Prohibits DRM

**Permissive Licenses**: Very few restrictions, allow for redistributing under other licenses, including closed source licenses
- **MIT, BSD, Apache 2.0**




