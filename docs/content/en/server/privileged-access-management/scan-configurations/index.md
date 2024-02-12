---
eleventyComputed:
  title: Scan configurations
  order: 30
---
The Scan Configurations or Account Discovery is the configured instance that will discover accounts of a provider's environment.  
![Account Discovery dialog](https://webdevolutions.azureedge.net/docs/en/server/ServerOp8143.png)

On the creation of an Account Discovery, it is possible to choose between [Domain](/server/privileged-access-management/providers/domain-provider/), [SQL Server](/server/privileged-access-management/scan-configurations/sql-account-discovery/), [SSH Local Accounts](/server/privileged-access-management/scan-configurations/ssh-account-discovery/), [Windows Users](/server/privileged-access-management/scan-configurations/windows-user-account-discovery/) or [Azure AD User](/server/privileged-access-management/scan-configurations/azure-ad-user-account-discovery/).  
![!!ServerOp8096](https://webdevolutions.azureedge.net/docs/en/server/ServerOp8096.png)

To see the results of the discovery process, click on the eye icon of the Account Discovery to see the list of accounts.  
![Account Discovery results dialog](https://webdevolutions.azureedge.net/docs/en/server/ServerOp8147.png)

To manage privileged accounts with the {{ en.DVLS }} PAM feature, select the accounts from the Account Discovery results page and click on the Import Selected Accounts button. Then the accounts will be available in Privileged Access section.  
![Import Selected Accounts operation](https://webdevolutions.azureedge.net/docs/en/server/ServerOp8148.png)

On import, the [Provider](/server/privileged-access-management/providers/), Destination Folder and Reset Password options can be set.  
![Import Window](https://webdevolutions.azureedge.net/docs/en/server/ServerOp8149.png)

### Import
| Option                    | Description                                                                     |
|---------------------------|---------------------------------------------------------------------------------|
| Provider                  | Select the Provider in the drop-down list.                                      |
| Folder                    | Select the destination folder in the drop-down list.                            |
| Reset Password On Import  | On import, the password will be reset.                                          |
| Reset Password On Check-In| When the user will release the account on Check-In, the password will be reset. |