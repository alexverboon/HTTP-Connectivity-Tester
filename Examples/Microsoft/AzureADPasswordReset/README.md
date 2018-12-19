# Azure Active Directory - Self Service Password Reset Connectivity Test

## Usage

1. Import this file: `Import-Module .\AzADSSPRConnectivity.psm1`
1. Run one of the following:
    * `$connectivity = Get-AzADSSPRConnectivity`
    * `$connectivity = Get-AzADSSPRConnectivity -Verbose`
    * `$connectivity = Get-AzADSSPRConnectivity -PerformBlueCoatLookup`
    * `$connectivity = Get-AzADSSPRConnectivity -Verbose -PerformBlueCoatLookup`
1. Filter results: `$connectivity | Format-List -Property Blocked,TestUrl,UnblockUrl,DnsAliases,IpAddresses,Description,Resolved,ActualStatusCode,ExpectedStatusCode,UnexpectedStatus`
1. Save results to a file: `Save-HttpConnectivity -Objects $connectivity -FileName ('AzADSSPRConnectivity_{0:yyyyMMdd_HHmmss}' -f (Get-Date))`

## Tested URLs

| Test URL | URL to Unblock | Description |
| -- | -- | -- |
| <https://passwordreset.microsoftonline.com> | <https://passwordreset.microsoftonline.com> |  URL used by Windows Clients behind a firewall to perform a Self Service Password Reset |
| <https://ajax.aspnetcdn.com> | <https://ajax.aspnetcdn.com> | URL used by Windows Clients behind a firewall to perform a Self Service Password Reset |


## References

* [Tutorial: Azure AD password reset from the login screen](https://docs.microsoft.com/en-us/azure/active-directory/authentication/tutorial-sspr-windows#limitations)
* 
