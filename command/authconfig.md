authconfig
===

集中式身份管理服务

## 补充说明

**authconfig命令** an interface for configuring system authentication resources。
下列内容来自CentOS8 authconfig --help。本人编写是没有找到man的相关内容

###  语法

```shell
authconfig(选项)(参数)
```

###  选项

```shell
usage: authconfig [-h] [--enablenis] [--disablenis] [--nisdomain <domain>]
                  [--nisserver <server>] [--enableldap] [--disableldap]
                  [--enableldapauth] [--disableldapauth]
                  [--ldapserver <server>] [--ldapbasedn <dn>]
                  [--enableldaptls] [--disableldaptls] [--enableldapstarttls]
                  [--disableldapstarttls] [--enablerfc2307bis]
                  [--disablerfc2307bis] [--enablesmartcard]
                  [--disablesmartcard] [--smartcardaction <0=Lock|1=Ignore>]
                  [--enablerequiresmartcard] [--disablerequiresmartcard]
                  [--enablefingerprint] [--disablefingerprint]
                  [--enableecryptfs] [--disableecryptfs] [--enablekrb5]
                  [--disablekrb5] [--krb5kdc <server>]
                  [--krb5adminserver <server>] [--krb5realm <realm>]
                  [--enablekrb5kdcdns] [--disablekrb5kdcdns]
                  [--enablekrb5realmdns] [--disablekrb5realmdns]
                  [--enablewinbind] [--disablewinbind] [--enablewinbindauth]
                  [--disablewinbindauth] [--winbindjoin <Administrator>]
                  [--enablewinbindkrb5] [--disablewinbindkrb5]
                  [--smbworkgroup <workgroup>] [--enablesssd] [--disablesssd]
                  [--enablesssdauth] [--disablesssdauth] [--enablecachecreds]
                  [--disablecachecreds] [--enablepamaccess]
                  [--disablepamaccess] [--enablemkhomedir]
                  [--disablemkhomedir] [--enablefaillock] [--disablefaillock]
                  [--passminlen <number>] [--passminclass <number>]
                  [--passmaxrepeat <number>] [--passmaxclassrepeat <number>]
                  [--enablereqlower] [--disablereqlower] [--enablerequpper]
                  [--disablerequpper] [--enablereqdigit] [--disablereqdigit]
                  [--enablereqother] [--disablereqother] [--nostart]
                  [--updateall] [--update] [--kickstart] [--test] [--probe]
                  [--savebackup <name>] [--restorebackup <name>]
                  [--restorelastbackup] [--enablecache] [--disablecache]
                  [--enableshadow] [--disableshadow] [--useshadow]
                  [--enablemd5] [--disablemd5] [--usemd5]
                  [--passalgo <descrypt|bigcrypt|md5|sha256|sha512>]
                  [--ldaploadcacert <URL>] [--smartcardmodule <module>]
                  [--smbsecurity <user|server|domain|ads>]
                  [--smbrealm <realm>] [--smbservers <servers>]
                  [--smbidmaprange <lowest-highest>]
                  [--smbidmapuid <lowest-highest>]
                  [--smbidmapgid <lowest-highest>] [--winbindseparator <\>]
                  [--winbindtemplatehomedir </home/%D/%U>]
                  [--winbindtemplateshell </bin/false>]
                  [--enablewinbindusedefaultdomain]
                  [--disablewinbindusedefaultdomain] [--enablewinbindoffline]
                  [--disablewinbindoffline] [--enablepreferdns]
                  [--disablepreferdns] [--enableforcelegacy]
                  [--disableforcelegacy] [--enablelocauthorize]
                  [--disablelocauthorize] [--enablesysnetauth]
                  [--disablesysnetauth] [--faillockargs <options>]

Authconfig Compatibility Tool.
  -h, --help                    帮助
  --enablenis                   默认使用 NIS 用户信息
  --disablenis                  默认禁用 NIS 用户信息
  --nisdomain <domain>          默认的 NIS 域
  --nisserver <server>          默认的 NIS 服务器
  --enableldap                  默认使用 LDAP 用户信息
  --disableldap                 默认禁用 LDAP 用户信息
  --enableldapauth              默认使用 LDAP 验证
  --disableldapauth             默认禁用 LDAP 验证
  --ldapserver <server>         默认的 NIS 服务器hostname或URI
  --ldapbasedn <dn>             默认的基于 DN 的 LDAP
  --enableldaptls               LDAP 使用 TLS (RFC-2830)
  --disableldaptls              LDAP 禁用 TLS (RFC-2830)
  --enableldapstarttls          enable use of TLS for identity lookups with LDAP
                                (RFC-2830)
  --disableldapstarttls
                                disable use of TLS for identity lookups with LDAP
                                (RFC-2830)
  --enablerfc2307bis            enable use of RFC-2307bis schema for LDAP user information lookups
  --disablerfc2307bis           disable use of RFC-2307bis schema for LDAP user information lookups
  --enablesmartcard             默认状态为启用智能卡验证  
  --disablesmartcard            默认禁用智能卡验证  
  --smartcardaction=<0=Lock|1=Ignore>
                                删除智能卡时进行的操作
  --enablerequiresmartcard      需要使用验证智能卡验证
                                默认
  --disablerequiresmartcard     不需要使用智能卡验证
                                默认
  --enablefingerprint           启用指纹验证
                                默认
  --disablefingerprint          禁用指纹验证
                                默认
  --enableecryptfs              enable automatic per-user ecryptfs
  --disableecryptfs             disable automatic per-user ecryptfs
  --enablekrb5                  默认启用 kerberos 验证
  --disablekrb5                 默认禁用 kerberos 验证
  --krb5kdc <server>            默认的 kerberos KDC
  --krb5adminserver <server>    默认的 kerberos 管理服务器
  --krb5realm=<realm>           默认的 kerberos 域
  --enablekrb5kdcdns            启用 DNS 来查找 kerberos KDCs
  --disablekrb5kdcdns           禁用 DNS 来查找 kerberos KDCs
  --enablekrb5realmdns          启用 DNS 来查找 kerberos 域
  --disablekrb5realmdns         禁用 DNS 来查找 kerberos 域 
  --enablewinbind               默认启用 winbind 来获取用户信息
  --disablewinbind              默认禁用 winbind 来获取用户信息
  --enablewinbindauth           默认启用 winbind 进行验证
  --disablewinbindauth          默认禁用 winbind 进行验证
  --winbindjoin <Administrator>
                                立即作为系统管理员加入 winbind 域或 ads域  
  --enablewinbindkrb5           使能winbind用Kerberos 5验证
  --disablewinbindkrb5          使能winbind用默认的方法验证 
  --smbworkgroup <workgroup>    验证服务器所在的组  
  --enablesssd                  enable SSSD for user information by default with manually managed configuration
  --disablesssd                 disable SSSD for user information by default (still used for supported configurations)
  --enablesssdauth              enable SSSD for authentication by default with manually managed configuration
  --disablesssdauth             disable SSSD for authentication by default (still used for supported configurations)  
  --enablecachecreds            enable caching of user credentials in SSSD by default
  --disablecachecreds           disable caching of user credentials in SSSD by default
  --enablepamaccess             在帐户验证过程中检查 access.conf
  --disablepamaccess            在帐户验证过程中不检查 access.conf
  --enablemkhomedir             使能用户第一次登录创建家目录
  --disablemkhomedir            失能用户第一次登录创建家目录	
  --enablefaillock              enable account locking in case of too many consecutive
                                authentication failures
  --disablefaillock             disable account locking in case of too many
  --passminlen <number>
                                minimum length of a password
  --passminclass <number>
                                minimum number of character classes in a password
  --passmaxrepeat <number>
                                maximum number of same consecutive characters in a
                                password
  --passmaxclassrepeat <number>
                                maximum number of consecutive characters of same class
                                in a password
  --enablereqlower              enable require at least one lowercase character in a
                                password
  --disablereqlower             disable require at least one lowercase character in a
                                password
  --enablerequpper              enable require at least one uppercase character in a
                                password
  --disablerequpper             disable require at least one uppercase character in a
                                passwor
  --enablereqdigit              enable require at least one digit in a password
  --disablereqdigit             disable require at least one digit in a password
  --enablereqother              enable require at least one other character in a
                                password
  --disablereqother             disable require at least one other character in a
                                password
  --nostart                     do not start/stop services
  --updateall                   update all configuration files
  --update                      the same as --updateall
  --kickstart                   the same as --updateall


These options are no longer supported and have no effect:
  --test
  --probe
  --savebackup <name>
  --restorebackup <name>
  --restorelastbackup
  --enablecache
      默认启用缓存用户信息，当SSSD使能时，自动失能
  --disablecache
      默认禁用缓存用户信息
  --enableshadow
      默认启用屏蔽口令
  --disableshadow
      默认禁用屏蔽口令
  --useshadow
  --enablemd5
      默认启用 MD5 口令
  --disablemd5
      默认禁用用 MD5 口令
  --usemd5
  --passalgo <descrypt|bigcrypt|md5|sha256|sha512>
      新密码使用加密算法
  --ldaploadcacert <URL>
      从这个 URL 加载 CA 证书
  --smartcardmodule <module>
      默认使用的智能卡模块
  --smbsecurity <user|server|domain|ads>
      samba 和 winbind 使用的安全模式
  --smbrealm <realm>
      当 security=ads 时，samba 和 winbind 的默认域
  --smbservers <servers>
      用来验证的服务器名称
  --smbidmaprange <lowest-highest>
      uid range winbind will assign to domain or ads users
  --smbidmapuid <lowest-highest>
      uid range winbind will assign to domain or ads users
  --smbidmapgid <lowest-highest>
      uid range winbind will assign to domain or ads users
  --winbindseparator <\>
      the character which will be used to separate the domain and user part of winbind-created user names if winbindusedefaultdomain is not enabled
  --winbindtemplatehomedir </home/%D/%U>
      winbind 创建的用户将会作为主目录的目录
  --winbindtemplateshell </bin/false>
      winbind创建的用户的shell将作为登录shell
  --enablewinbindusedefaultdomain
      configures winbind to assume that users with no domain in their user names are domain users
  --disablewinbindusedefaultdomain
      configures winbind to assume that users with no domain in their user names are not domain users
  --enablewinbindoffline
      将 winbind 配置为允许离线登录
  --disablewinbindoffline
      将 winbind 配置为阻止离线登录
  --enablepreferdns
      prefer dns over wins or nis for hostname resolution
  --disablepreferdns
      do not prefer dns over wins or nis for hostname resolution
  --enableforcelegacy
      never use SSSD implicitly even for supported configurations
  --disableforcelegacy
      use SSSD implicitly if it supports the configuration
  --enablelocauthorize
      本地用户可以使用本地授权
  --disablelocauthorize
      通过远端服务授权本地用户
  --enablesysnetauth
      通过网络服务认证的系统帐号
  --disablesysnetauth
      仅通过本地文件认证的系统帐号
  --faillockargs <options>

```

###  参数

集中式身份管理服务：面对多计算机的身份管理以及账户信息同步, 其解决方案并不是把信息存放在本地, 而是存放在一台提供验证服务的服务器上。凭借SSO, 用户输入密码进行一次性身份验证即可获得用于向其他服务进行身份验证的一种票据或cookie。


<!-- Linux命令行搜索引擎：https://jaywcjlove.github.io/linux-command/ -->
