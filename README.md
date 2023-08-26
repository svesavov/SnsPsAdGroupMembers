
###### If you like it, please consider buy me a beer :beer:
###### [![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=6NKR7XQH5E2P2&source=url)


# SnsPsAdGroupMembers PowerShell Module

* This is a binary PowerShell module for automatic on premises Active Directory group members management. In general the PowerShell binary CmdLets are much faster comparing with the written-on PowerShell ones.
* The SnsPsAdGroupMembers PowerShell Module uses AD attributes-based logic with LDAP syntax for managing the AD group members.
* The SnsPsAdGroupMembers PowerShell Module supports different logic for adding members than removing members.
* The SnsPsAdGroupMembers PowerShell Module supports inclusions and exclusions.
* The SnsPsAdGroupMembers PowerShell Module does have reporting capabilities. Reporting the actions taken over the groups to their respective owners is the main factor the group members automation success.
* The SnsPsAdGroupMembers PowerShell Module uses SQLite databases to store the managed ad groups configuration and the events that happen during the groups management. Both DataBases are originally located at C:\ProgramData\SnsAdGroupMembers. If you need to change their location please refer to the comments within the PowerShell module .PSM1 file.


## Features

* Progress Bar is visible only when a CmdLet is executed interactively. This improves the performance of the scripts and the automations running as a service on a schedule.

* Working with the pipeline. Using "begin", "process" and "end" methods improves the performance.

* Built-in performance measurement accessible via Verbose stream.

* Reports intended to be provided to the group owners and the company IT's.

* Blocking of the members removal whenever the percentage of the members evaluated for removal is above certain percentage.

* Stores a constant value in an attribute of the managed groups for easy identifying the managed groups. This feature is disabled by default, to enable it, specify an AD attribute and a value that have to be set in that attribute. 

* Options to make only members removal or only members adding. This feature is particularly useful when AD Group membership requires formal approval process for adding. Using automated removal for such groups leaves no option for "forgotten" members when they leave the company or change their position which no longer requires membership of those groups.

* Uses Active Directory attributes-based LDAP Syntax to specify the adding and removing logic. For best results use it in conjunction a synchronization from the company HR tool. Mosta of the HR tools provides out of the box synchronization applications. In case the HR tool is on premises one, synchronization tool can be easily created using a PowerShell Module about working with the DataBase used by the HR tool.

* Uses own AD cache to prevent repeatable queries against the domain controllers.

* The managed group configuration settings and logic is kept in a way that exclude errors in case of rename or AD objects move between the AD Organizational Units.

For additional information, please use the CmdLets built-in help.
```powershell
Get-Help Add-SnsAdManagedGroupContact -Full;
Get-Help Add-SnsAdManagedGroupExclusion -Full;
Get-Help Add-SnsAdManagedGroupInclusion -Full;
Get-Help Clear-SnsAdManagedGroupContact -Full;
Get-Help Clear-SnsAdManagedGroupExclusion -Full;
Get-Help Clear-SnsAdManagedGroupInclusion -Full;
Get-Help Get-SnsAdGroupMembersPsModuleSettings -Full;
Get-Help Get-SnsAdManagedGroup -Full;
Get-Help Invoke-SnsAdGroupMembersManage -Full;
Get-Help Invoke-SnsStatisticsDataBaseDefragmentation -Full;
Get-Help New-SnsAdManagedGroup -Full;
Get-Help Remove-SnsAdManagedGroup -Full;
Get-Help Remove-SnsAdManagedGroupContact -Full;
Get-Help Remove-SnsAdManagedGroupExclusion -Full;
Get-Help Remove-SnsAdManagedGroupInclusion -Full;
Get-Help Set-SnsAdGroupMembersPsModuleSettings -Full;
Get-Help Set-SnsAdManagedGroup -Full;
Get-Help Set-SnsAdManagedGroupContact -Full;
Get-Help Set-SnsAdManagedGroupExclusion -Full;
Get-Help Set-SnsAdManagedGroupInclusion -Full;
```


## Requirements

* .NET Framework 4.8
* PowerShell 4


## Instructions

Simply run
```powershell
Install-Module "SnsPsAdGroupMembers" -Scope "AllUsers";
```
OR
1. Download SnsPsAdGroupMembers.zip.
2. Don't forget to check the .ZIP file for viruses and etc.
3. File MD5 hash: `19C048172DF8C1C7445D7A059903E5EB`
4. Unzip in one of the following folders depending of your preference:
* `C:\Users\UserName\Documents\WindowsPowerShell\Modules` - Replace "UserName" with the actual username If you want the module to be available for specific user. Not recommended.
* `C:\Program Files\WindowsPowerShell\Modules` - If you want the module to be available for all users on the machine.
* Or any other location present in `$env:PSModulePath`
5. Run the following command replacing "PathWhereModuleIsInstalled" with the actual path where the module files were unzipped.
```powershell
Get-ChildItem -Path "PathWhereModuleIsInstalled" -Recurse | Unblock-File
```


## Notes

* To Ensure The Smooth Operation Of "SnsPsAdGroupMembers" PSModule Install It With "AllUsers" Scope. The Idea Behind This Module Is To Be Used On A Scheduled Task "As Service" For The Actual Group Members Management, And Interactively By IT Administrators To Create And Modify The Managed Groups Configuration. This Requires The PSModule To Be Available To Multiple User Accounts.

* To Ensure The Smooth Creation Of "SnsPsAdGroupMembers" PSModule DataBases, The First Load Of The PSModule Must Be In Elevated Mode. In The Normal Operation The PSModule Does Not Require Elevated Mode.


## External Links

- svesavov on GitHub: [https://github.com/svesavov](https://github.com/svesavov)
- svesavov on PowerShell Gallery: [https://www.powershellgallery.com/packages/SnsPsAdGroupMembers/](https://www.powershellgallery.com/packages/SnsPsAdGroupMembers/)
- Svetoslav Savov on LinkedIn: [https://www.linkedin.com/in/svetoslavsavov](https://www.linkedin.com/in/svetoslavsavov)

