---
eleventyComputed:
  title: Deleted entries
  description: The Deleted Entries will generate a list containing all the entries previously deleted from your data source.
---
The ***Administration – Deleted Entries*** option allows you to view the deleted entries as well as restoring them.  

{% snippet icon.badgeInfo %} 
This feature requires an [Advanced Data Source](/rdm/windows/data-sources/data-sources-types/advanced-data-sources/). 
{% endsnippet %}
 
{% snippet icon.badgeInfo %} 
Administrators can permanently delete some or all deleted entries. 
{% endsnippet %} 

## Settings 

### Manage deleted entries 

The ***Deleted Entries*** will generate a list containing all the entries previously deleted from your data source. You may restore an entry, meaning it will become an active entry again and will be shown in your data source. You may also chose to permanently delete your entries, once you have permanently deleted your entries you will not be able to restore them afterward.  
![Deleted Entries](https://webdevolutions.azureedge.net/docs/en/rdm/windows/clip10308.png) 

<table>
	<tr>
		<th>
OPTION 
		</th>
		<th>
DESCRIPTION 
		</th>
	</tr>
	<tr>
		<td>
Delete 
		</td>
		<td>
Permanently delete the selected entry. 
		</td>
	</tr>
	<tr>
		<td>
Restore Entry 
		</td>
		<td>
Use this button to restore an entry. 
		</td>
	</tr>
	<tr>
		<td>
Delete All 
		</td>
		<td>
Permanently delete all the deleted entries. 
		</td>
	</tr>
</table>

{% snippet icon.badgeNotice %} 
Deleted entries can be restored as long as the [Security Provider](/rdm/windows/commands/administration/settings/security-providers/) has not been changed since the deleted action. 
{% endsnippet %}
 
### Export deleted entries list 

You can right-click on one or several lines to export them in CSV, HTML, or XML format. 