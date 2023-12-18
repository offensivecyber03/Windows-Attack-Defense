# Kerberoasting
In Active Directory, a Service Principal Name (SPN) is a unique service instance identifier. Kerberos uses SPNs for authentication to associate a service instance with a service logon account, which allows a client application to request that the service authenticate an account even if the client does not have the account name. When a Kerberos TGS service ticket is asked for, it gets encrypted with the service account's NTLM password hash.

Kerberoasting is a post-exploitation attack that attempts to exploit this behavior by obtaining a ticket and performing offline password cracking to open the ticket. If the ticket opens, then the candidate password that opened the ticket is the service account's password. The success of this attack depends on the strength of the service account's password. 