# Active Directory Things

### Meaning of Windows' AD "userAccountControl" attribute
 
```c++
typedef enum  {
  ADS_UF_SCRIPT                                   = 1,         // 0x1
  ADS_UF_ACCOUNTDISABLE                           = 2,         // 0x2
  ADS_UF_HOMEDIR_REQUIRED                         = 8,         // 0x8
  ADS_UF_LOCKOUT                                  = 16,        // 0x10
  ADS_UF_PASSWD_NOTREQD                           = 32,        // 0x20
  ADS_UF_PASSWD_CANT_CHANGE                       = 64,        // 0x40
  ADS_UF_ENCRYPTED_TEXT_PASSWORD_ALLOWED          = 128,       // 0x80
  ADS_UF_TEMP_DUPLICATE_ACCOUNT                   = 256,       // 0x100
  ADS_UF_NORMAL_ACCOUNT                           = 512,       // 0x200
  ADS_UF_INTERDOMAIN_TRUST_ACCOUNT                = 2048,      // 0x800
  ADS_UF_WORKSTATION_TRUST_ACCOUNT                = 4096,      // 0x1000
  ADS_UF_SERVER_TRUST_ACCOUNT                     = 8192,      // 0x2000
  ADS_UF_DONT_EXPIRE_PASSWD                       = 65536,     // 0x10000
  ADS_UF_MNS_LOGON_ACCOUNT                        = 131072,    // 0x20000
  ADS_UF_SMARTCARD_REQUIRED                       = 262144,    // 0x40000
  ADS_UF_TRUSTED_FOR_DELEGATION                   = 524288,    // 0x80000
  ADS_UF_NOT_DELEGATED                            = 1048576,   // 0x100000
  ADS_UF_USE_DES_KEY_ONLY                         = 2097152,   // 0x200000
  ADS_UF_DONT_REQUIRE_PREAUTH                     = 4194304,   // 0x400000
  ADS_UF_PASSWORD_EXPIRED                         = 8388608,   // 0x800000
  ADS_UF_TRUSTED_TO_AUTHENTICATE_FOR_DELEGATION   = 16777216   // 0x1000000
} ADS_USER_FLAG_ENUM;
```

* ADS_UF_SCRIPT
>The logon script is executed. This flag does not work for the ADSI LDAP provider on either read or write operations. For the ADSI WinNT provider, this flag is read-only data, and it cannot be set for user objects.

* ADS_UF_ACCOUNTDISABLE
> The user account is disabled.

* ADS_UF_HOMEDIR_REQUIRED
> The home directory is required.

* ADS_UF_LOCKOUT
> The account is currently locked out.

* ADS_UF_PASSWD_NOTREQD
> No password is required.

* ADS_UF_PASSWD_CANT_CHANGE
> The user cannot change the password. This flag can be read, but not set directly. For more information and a code example that shows how to prevent a user from changing the password, see User Cannot Change Password.

* ADS_UF_ENCRYPTED_TEXT_PASSWORD_ALLOWED
> The user can send an encrypted password.

* ADS_UF_TEMP_DUPLICATE_ACCOUNT
> This is an account for users whose primary account is in another domain. This account provides user access to this domain, but not to any domain that trusts this domain. Also known as a local user account.

* ADS_UF_NORMAL_ACCOUNT
> This is a default account type that represents a typical user.

* ADS_UF_INTERDOMAIN_TRUST_ACCOUNT
> This is a permit to trust account for a system domain that trusts other domains.

* ADS_UF_WORKSTATION_TRUST_ACCOUNT
> This is a computer account for a Windows 2000 Professional or Windows 2000 Server that is a member of this domain.

* ADS_UF_SERVER_TRUST_ACCOUNT
> This is a computer account for a system backup domain controller that is a member of this domain.

* ADS_UF_DONT_EXPIRE_PASSWD
> When set, the password will not expire on this account.

* ADS_UF_MNS_LOGON_ACCOUNT
> This is an Majority Node Set (MNS) logon account. With MNS, you can configure a multi-node Windows cluster without using a common shared disk.

* ADS_UF_SMARTCARD_REQUIRED
> When set, this flag will force the user to log on using a smart card.

* ADS_UF_TRUSTED_FOR_DELEGATION
> When set, the service account (user or computer account), under which a service runs, is trusted for Kerberos delegation. Any such service can impersonate a client requesting the service. To enable a service for Kerberos delegation, set this flag on the userAccountControl property of the service account.

* ADS_UF_NOT_DELEGATED
> When set, the security context of the user will not be delegated to a service even if the service account is set as trusted for Kerberos delegation.

* ADS_UF_USE_DES_KEY_ONLY
> Restrict this principal to use only Data Encryption Standard (DES) encryption types for keys. 
>> Active Directory Client Extension:  Not supported.

* ADS_UF_DONT_REQUIRE_PREAUTH
> This account does not require Kerberos preauthentication for logon.
>> Active Directory Client Extension:  Not supported.

* ADS_UF_PASSWORD_EXPIRED
> The user password has expired. This flag is created by the system using data from the password last set attribute and the domain policy. It is read-only and cannot be set. To manually set a user password as expired, use the NetUserSetInfo function with the USER_INFO_3(usri3_password_expired member) or USER_INFO_4 (usri4_password_expired member) structure.
 >> Active Directory Client Extension:  Not supported.

* ADS_UF_TRUSTED_TO_AUTHENTICATE_FOR_DELEGATION
> The account is enabled for delegation. This is a security-sensitive setting; accounts with this option enabled should be strictly controlled. This setting enables a service running under the account to assume a client identity and authenticate as that user to other remote servers on the network.
 >> Active Directory Client Extension:  Not supported.