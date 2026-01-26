# Random Windows XP Notes
You would be foolish to assume anything here works *after* Windows XP, and really I can't guarantee this stuff actually works in Windows XP.

### IE6 Notes
* Force IE6 reinstall
> `rundll32.exe setupapi,InstallHinfSection DefaultInstall 132 C:\windows\inf\ie.inf`
 

### `netsh` notes
* This command can manipulate most things network; see `netsh /?`
* TCP/Winsock resets - for strange network/TCP issues
> `netsh int ip reset resetlog.txt`
> `netsh winsock reset catalog`

### Registry Notes
* `REG` - lets you query and modify the registry from the command line
  * `ADD` - Add non-existent keys
    * '/v' - Value to add
	* '/t' - Value data type
	* '/d' - Data to add
	* '/f' - Force overwrite
  * `QUERY` - dump keys to stdout
    * `/s` - recurse

* Enable `REGEDIT` if it has been disabled through policy
> `REG ADD HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\System /v DisableRegistryTools /t REG_DWORD /d 0 /f`

* Enable `TASKMGR` if it has been disabled through policy
> `REG ADD HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\System /v DisableTaskMgr /t REG_DWORD /d 0 /f`

* Show (network?) Printer registry settings
>  `REG QUERY "HKCU\Printers\Connections\"`

* Show Windows User Profile keys
>  `REG QUERY "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList" /s`

* Show Outlook profile keys
>  `REG QUERY "HKCU\Software\Microsoft\Windows NT\Current Version\Windows Messaging Subsystem\Profiles" /s`

* Show Mapped network drives
>  `REG QUERY "HKCU\Network" /s`

* Show TCPIP parameters rewritten by `netsh int ip reset`
>  `REG QUERY "HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\"`
>  `REG QUERY "HKLM\SYSTEM\CurrentControlSet\Services\DHCP\Parameters\"`

* Show IE6 Internet Zone Settings
>  `REG QUERY "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap" /s`
>  `REG QUERY "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones" /s`

* Meaning of bits in key `HKLM\Software\Microsoft\Windows NT\CurrentVersion\ProfileList\SID State`:
 ```
    #define PROFILE_MANDATORY       0x00000001
    #define PROFILE_USE_CACHE       0x00000002
    #define PROFILE_NEW_LOCAL       0x00000004
    #define PROFILE_NEW_CENTRAL     0x00000008
    #define PROFILE_UPDATE_CENTRAL  0x00000010
    #define PROFILE_DELETE_CACHE    0x00000020
    // do not define bit 40 because NT4 has this defined as Run_SyncApps.
    #define PROFILE_GUEST_USER      0x00000080
    #define PROFILE_ADMIN_USER      0x00000100
    #define DEFAULT_NET_READY       0x00000200
    #define PROFILE_SLOW_LINK       0x00000400
    #define PROFILE_TEMP_ASSIGNED   0x00000800
    // do not define bit 1000, this was used briefly 2009, 2010 before
    #define PROFILE_PARTLY_LOADED   0x00002000
    #define PROFILE_BACKUP_EXISTS   0x00004000
    #define PROFILE_THIS_IS_BAK     0x00008000
```

### Miscellaneous
* Show installed file system minifilters
>`fltmc`
