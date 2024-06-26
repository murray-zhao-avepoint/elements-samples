# Elements.Client - the PowerShell module for the Elements API

Portal Api HTTP API V1

This PowerShell module is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: v1
- SDK version: 2.0.26
- Build package: org.openapitools.codegen.languages.PowerShellClientCodegen

<a id="frameworks-supported"></a>
## Frameworks supported
- PowerShell 5.1 or later

<a id="installation"></a>
## Installation

To install from PowerShell Gallery (https://www.powershellgallery.com/packages/Elements.Client), run the following command
```powershell
Install-Module -Name Elements.Client -Verbose
```

To uninstall the module, simply run:
```powershell
Uninstall-Module -Name Elements.Client -RequiredVersion 2.0.26
```

<a name="how-to-use"></a>
## How to Use
### 1. [**Connect-Elements**](docs/ElementsConnectApi.md#connect-elements)
To use Elements PowerShell Client, you need to connect to Elements public API with PowerShell:
```powershell
Connect-Elements -Url "Elements Public API URL" -ClientId "Application Client Id from Elements" -Cert $certificate
```
You can construct the $certificate parameter by the following two ways:
```powershell
# Get from .pfx file with the password
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2 "path_to_pfx_file", "password"

# Get from certificate store of local machine by certificate thumbprint, you need install the certificate to local machine in advance and replace the certificate thumbprint to yours
$certificate = (Get-ChildItem -Path 'Cert:\LocalMachine\My\your thumbprint' -Recurse)[0]
```
Or use the Client Secret to connect
```powershell
Connect-Elements -Url "Elements Public API URL" -ClientId "Application Client Id from Elements" -ClientSecret "Application Client Secret from Elements"
```
After you connect to Elements public API, then you can perform various operations like getting customer status, customer job status,etc.


## Documentation for API Endpoints

### 1. [**Get-ElementsCustomer**](docs/ElementsCustomersApi.md#get-elementscustomer)
Use the following PowerShell command to get the general information of the customers that you manage:
```powershell
Get-ElementsCustomer
```

### 2. [**Get-ElementsCustomerJob**](docs/ElementsCustomersApi.md#get-elementscustomerjob)
Use the following PowerShell command to get the job information of a specific customer that you manage:
```powershell
Get-ElementsCustomerJob -Id 'Customer Id'
```
The ```-Id``` parameter is the tenant owner ID of the customer.

### 3. [**Get-ElementsCustomerProtected**](docs/ElementsCustomersApi.md#get-elementscustomerprotected)
Use the following PowerShell command to get the general information of a specific customer that you manage:
```powershell
Get-ElementsCustomerProtected -Id 'Customer Id'
```
The ```-Id``` parameter is the tenant owner ID of the customer. 

### 4. [**Get-ElementsCustomerServices**](docs/ElementsCustomersApi.md#get-elementscustomerservices)
Use the following PowerShell command to get the subscription details of different services for the customers that you manage:
```powershell
Get-ElementsCustomerServices
```
### 5. [**Get-ElementsCustomerScanProfile**](docs/ElementsCustomersApi.md#get-elementscustomerscanprofile)
Use the following PowerShell command to get the profiles for the customers that you manage:
```powershell
Get-ElementsCustomerScanProfile
```
### 6. [**Get-ElementsCustomerScanProfileDailyNew**](docs/ElementsCustomersApi.md#get-elementscustomerscanprofiledailynew)
Use the following PowerShell command to get the changes summary of the Scan Profile :
```powershell
Get-ElementsCustomerScanProfileDailyNew
```
### 7. [**Get-ElementsCustomerScanProfileDailyNewDetail**](docs/ElementsCustomersApi.md#get-elementscustomerscanprofiledailynewdetail)
Use the following PowerShell command to get the changes objects of the Scan Profile :
```powershell
Get-ElementsCustomerScanProfileDailyNewDetail
```
## FAQ

- **Q**: What can I do if there is a 401(Unauthorized) error?
  - **A**: This error code means your access token is expired, normally the token is valid for one hour, you need run [**Connect-Elements**](docs/ElementsConnectApi.md#connect-elements) to retrieve the access token again, then continue with the other cmdlets.

## About Elements 

[AvePoint Elements](https://www.avepointonlineservices.com) Accelerate cloud adoption and usage by delivering comprehensive coverage for Microsoft 365 with enterprise grade software in addition to data protection for Google Workspace, Dynamics 365, and Salesforce. Elements, AvePoint's partner-centric portal allows you to streamline operational efficiencies. Easily provision, manage, and analyze your customer licenses and usage all in one place. Provision at scale without losing visibility into support tickets and ongoing activity.