---
_schema: default
eleventyComputed:
  title: Getting started
  description: Although each Devolutions PowerShell script has specific dependencies related to the tasks it is meant to carry out, all must meet certain minimum requirements in order to be executed at all. Luckily, these prerequisites only need to be configured once per machine.
  order: 20
  status:
  keywords:
---
Although each Devolutions PowerShell script has specific dependencies related to the tasks it is meant to carry out, all must meet certain minimum requirements in order to be executed at all. Luckily, these prerequisites only need to be configured once per machine.

{% snippet, "badgeInfo" %}In order for Devolutions.PowerShell module to work with the desired solution, both need to be installed on the same machine.{% endsnippet %}

#### Installing PowerShell v7+

There are two types of PowerShell: Windows PowerShell and just plain PowerShell. The former is installed by default on every version of Windows but the latter is not and therefore requires a separate installation. Since Devolutions' products only support PowerShell proper, it will need to be installed manually.

To so, head over to the [Microsoft's PowerShell GitHub repository releases page](https://github.com/PowerShell/PowerShell/releases), scroll down the Assets section, and dowload the Windows .msi package.

![Windows .msi package from the Assets list](https://cdnweb.devolutions.net/docs/INTERFACE4042.png "Windows .msi package from the Assets list")

#### User's execution policy

The user under which PowerShell executes scripts must have certain permissions. To get them, open PowerShell and run the command `Get-ExecutionPolicy` for the current execution policy. If the policy is set to RemoteSigned, change it to **Unrestricted** using the `Set-ExecutionPolicy` command.

![Setting the ExecutionPolicy to Unrestricted](https://cdnweb.devolutions.net/docs/INTERFACE4045.png "Setting the ExecutionPolicy to Unrestricted")

#### Installing Devolutions' PowerShell module

To install Devolutions's PowerShell module, run the `Install-Module Devolutions.PowerShell` script.

A prompt should then appear asking you to trust a PSGallery repository. Enter `Yes` to accept.

![Installing Devolutions.PowerShell](https://cdnweb.devolutions.net/docs/INTERFACE4046.png "Installing Devolutions.PowerShell")

If the installation went smoothly, running the `Get-Command -Module Devolutions.PowerShell` script should return all Devolutions.PowerShell commands.

![List of all the Devolutions.PowerShell commands](https://cdnweb.devolutions.net/docs/INTERFACE4048.png "List of all the Devolutions.PowerShell commands")

### Testing connection to a data source

With the module installed, the next step is to verify the connection to a Devolutions data source. To do this, run the `Get-RDMCurrentDatasource` script.

![Successful connection to an SQLite data source](https://cdnweb.devolutions.net/docs/INTERFACE4047.png "Successful connection to an SQLite data source")f

If {% var, "RDM" false %} is installed on the machine, running `Get-RDMEntry` should return a list of all the available entries, which means the connection to the data source is properly established, queries can be made, and scripts can from then on be executed seamlessly.

&nbsp;

&nbsp;

&nbsp;