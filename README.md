# PatchTuesday
SysAdmin Notes for Patch Tuesdays... chance of PowerShell scripts 60%

## PowerShell

```PowerShell
# Get list of applications for a single or multiple remote servers
$serverlist = "Server01"
$serverlist = "Server01","Server02","Server03"

Get-CimInstance -ComputerName $serverlist -Namespace root\ccm\clientsdk -ClassName CCM_Application | select -Property Name,ApplicabilityState,ConfigureState,PSComputerName -ExcludeProperty Icon | sort PSComputerName,Name

<# Members 
PSShowComputerName         NoteProperty bool PSShowComputerName=True
AllowedActions             Property     string[] AllowedActions {get;set;}
AppDTs                     Property     CimInstance#InstanceArray AppDTs {get;set;}
ApplicabilityState         Property     string ApplicabilityState {get;set;}
ApplicationType            Property     uint32 ApplicationType {get;set;}
Categories                 Property     string[] Categories {get;set;}
ConfigureState             Property     string ConfigureState {get;set;}
ContentSize                Property     uint32 ContentSize {get;set;}
Deadline                   Property     CimInstance#DateTime Deadline {get;set;}
DeploymentReport           Property     string DeploymentReport {get;set;}
Description                Property     string Description {get;set;}
EnforcePreference          Property     uint32 EnforcePreference {get;set;}
ErrorCode                  Property     uint32 ErrorCode {get;set;}
EstimatedInstallTime       Property     uint32 EstimatedInstallTime {get;set;}
EvaluationState            Property     uint32 EvaluationState {get;set;}
FileTypes                  Property     string FileTypes {get;set;}
FullName                   Property     string FullName {get;set;}
HighImpactDeployment       Property     bool HighImpactDeployment {get;set;}
Icon                       Property     string Icon {get;set;}
Id                         Property     string Id {get;set;}
InformativeUrl             Property     string InformativeUrl {get;set;}
InfoUrlText                Property     string InfoUrlText {get;set;}
InProgressActions          Property     string[] InProgressActions {get;set;}
InstallState               Property     string InstallState {get;set;}
IsMachineTarget            Property     bool IsMachineTarget {get;set;}
IsPreflightOnly            Property     bool IsPreflightOnly {get;set;}
LastEvalTime               Property     CimInstance#DateTime LastEvalTime {get;set;}
LastInstallTime            Property     CimInstance#DateTime LastInstallTime {get;set;}
Name                       Property     string Name {get;set;}
NextUserScheduledTime      Property     CimInstance#DateTime NextUserScheduledTime {get;set;}
NotifyUser                 Property     bool NotifyUser {get;set;}
OverrideServiceWindow      Property     bool OverrideServiceWindow {get;set;}
PercentComplete            Property     uint32 PercentComplete {get;set;}
PrivacyUri                 Property     string PrivacyUri {get;set;}
PSComputerName             Property     string PSComputerName {get;}
Publisher                  Property     string Publisher {get;set;}
RebootOutsideServiceWindow Property     bool RebootOutsideServiceWindow {get;set;}
ReleaseDate                Property     CimInstance#DateTime ReleaseDate {get;set;}
ResolvedState              Property     string ResolvedState {get;set;}
Revision                   Property     string Revision {get;set;}
SoftwareVersion            Property     string SoftwareVersion {get;set;}
StartTime                  Property     CimInstance#DateTime StartTime {get;set;}
SupersessionState          Property     string SupersessionState {get;set;}
Type                       Property     uint32 Type {get;set;}
UserUIExperience           Property     bool UserUIExperience {get;set;}
#>
```

```PowerShell
# Get list patches and updates via CCM
Get-CimInstance -ComputerName $serverlist -Namespace root\ccm\clientsdk -ClassName CCM_SoftwareUpdate | select -Property Name,PSComputerName -ExcludeProperty Icon | sort PSComputerName,Name

<# Members
ArticleID                   Property     string ArticleID {get;set;}
BulletinID                  Property     string BulletinID {get;set;}
ComplianceState             Property     uint32 ComplianceState {get;set;}
ContentSize                 Property     uint32 ContentSize {get;set;}
Deadline                    Property     CimInstance#DateTime Deadline {get;set;}
Description                 Property     string Description {get;set;}
ErrorCode                   Property     uint32 ErrorCode {get;set;}
EstimatedInstallTime        Property     uint32 EstimatedInstallTime {get;set;}
EvaluationState             Property     uint32 EvaluationState {get;set;}
ExclusiveUpdate             Property     bool ExclusiveUpdate {get;set;}
FullName                    Property     string FullName {get;set;}
IsO365Update                Property     bool IsO365Update {get;set;}
IsUpgrade                   Property     bool IsUpgrade {get;set;}
MaxExecutionTime            Property     uint32 MaxExecutionTime {get;set;}
Name                        Property     string Name {get;set;}
NextUserScheduledTime       Property     CimInstance#DateTime NextUserScheduledTime {get;set;}
NotifyUser                  Property     bool NotifyUser {get;set;}
OverrideServiceWindows      Property     bool OverrideServiceWindows {get;set;}
PercentComplete             Property     uint32 PercentComplete {get;set;}
PSComputerName              Property     string PSComputerName {get;}
Publisher                   Property     string Publisher {get;set;}
RebootOutsideServiceWindows Property     bool RebootOutsideServiceWindows {get;set;}
RestartDeadline             Property     CimInstance#DateTime RestartDeadline {get;set;}
StartTime                   Property     CimInstance#DateTime StartTime {get;set;}
Type                        Property     uint32 Type {get;set;}
UpdateID                    Property     string UpdateID {get;set;}
URL                         Property     string URL {get;set;}
UserUIExperience            Property     bool UserUIExperience {get;set;}
#>
```
