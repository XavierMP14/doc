---
_schema: default
eleventyComputed:
  title: Pre-deployment account survey
  description: >-
    Prior to deployment of a {{ en.DVLS }} instance, some accounts are needed to
    operate the various services involved in a secure deployment of {{ en.DVLS
    }}.
  status: Topic available in German language
---
Prior to deployment of a {{ en.DVLS }} instance, some accounts are needed to operate the various services involved in a secure deployment of {{ en.DVLS }}. The first decision is to use either domain accounts for operating the platform, or to use local SQL accounts paired with local service accounts. Since this decision is a matter of personal preference, we support both models.

{% snippet, "badgeInfo" %}
Before proceeding, please take the following into account:
* The names used in this guide are to ease comprehension of the role fulfilled by the account. Our documentation uses these names as well, but there is no requirement that you use them.
* The following accounts interacting with the SQL database will be granted the least privileges permissions from scripts that will run during the creation and the upgrade of the {{ en.DVLS }} instance.
{% endsnippet %}

## Domain-based operation (integrated security option)

The ***Administration credentials*** needs full read permissions on the AD structure, but does NOT perform any changes to your directory. Sadly, because of a side effect of how the net Directory Services are built, there is an issue when that account tries to read properties of AD groups that may reside in a protected area of your directory. The easiest fix was to grant full admin permissions, but we are looking into implementing a better fallback strategy to handle the case where access is denied. It may require higher privileges than being part of the Domain Users built-in Active Directory group. In most cases, it should be sufficient.

&nbsp;

<table><thead><tr><th><p>Name</p></th><th><p>ORIGIN</p></th><th><p>DESCRIPTION</p></th><th><p>SET IN...</p></th></tr></thead><tbody><tr><td><p>VaultDBOwner</p></td><td><p>AD</p></td><td><p>Account with full privileges on the DB</p></td><td><p>Interactive Windows session used to run the installation/upgrade of a {% var, "DVLS" false %} instance. This account must be a local administrator of the {% var, "DVLS" false %}host machine.</p></td></tr><tr><td><p>VaultDBRunner</p></td><td><p>AD</p></td><td><p>Least-privileged account to run the web application. Used to connect to the Database and to read from the file system.</p></td><td><p>IIS Application pools that are running a {% var, "DVLS" false %} Instance.</p></td></tr><tr><td><p>VaultADReader</p></td><td><p>AD</p></td><td><p>Least-privileged account to query the AD.</p></td><td><p><em><strong>{% var, "DVLS" false %} Instance Settings - Administration credentials.</strong></em></p></td></tr><tr><td><p>VaultDBSchedulerService<br /></p></td><td><p>AD</p></td><td><p>Least-privileged account to operate the scheduler service. Used to connect to the DB and to read/write from the file system.</p></td><td><p>Windows Service Control Manager.</p></td></tr></tbody></table>

## Non-domain based operation or Azure SQL environment

On a non-domain-based deployment, a single connection string is used for three different aspects of the system. This will be improved in a future release to respect the least-privilege principle.

For Azure SQL hosted database, domain-based operation (integrated security option) is not supported.

\| \# \| Name \| Origin \| Description \| Set in... \| \| - \| ----------------------- \| ------ \| --------------------------------------------------------------------------------------------------- \| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- \| \| 1 \| VaultDBOwner \| SQL \| Account with full privileges on the DB. \| The {{ en.DVLSCONSOLE }} only for installation/upgrade sessions. \| \| 2 \| VaultDBRunner \| SQL \| Least-privileged account to run the web application. \| The {{ en.DVLSCONSOLE }} for operations of the instance. \| \| 3 \| VaultADReader \| AD \| Least-privileged account to query the AD through LDAP. \| {{ en.DVLS }} Instance Settings - Administration credentials. \| \| 4 \| VaultDBSchedulerService \| SQL \| Least-privileged account to operate the scheduler service. Used to read/write from the file system. \| {{ en.DVLSCONSOLE }} – Scheduler service. The database access will be performed by the single ConnectionString that is the subject of the informational note above. \|