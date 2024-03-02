# Find Shared Mailboxes with Licenses in Office 365

## Overview

This PowerShell script is designed to export information about licensed shared mailboxes in Office 365. It checks for the availability of required modules, connects to Exchange Online and Azure AD, and then retrieves details about shared mailboxes with assigned licenses. The results are exported to a CSV file, and the user has the option to open the file after execution.

## Usage

### Parameters

- **NoMFA**: Optional switch parameter to indicate non-MFA (Multi-Factor Authentication) mode.
- **UserName**: Optional parameter for providing the username when using non-MFA.
- **Password**: Optional parameter for providing the password when using non-MFA.

### Module Installation

The script checks for the existence of the required modules, namely ExchangeOnlineManagement and MSOnline. If these modules are not found, the script prompts the user for installation.

### Authentication

Authentication is handled differently based on the presence of the NoMFA switch. In non-MFA mode, the script either uses provided credentials or prompts the user for credentials. In MFA mode, it connects to Exchange Online and Azure AD without requiring additional credentials.

## Execution

The main function, `Connect_Modules`, ensures that the necessary modules are installed and establishes connections to Exchange Online and Azure AD. The script then retrieves licensed shared mailboxes and exports relevant details to a CSV file.

### Output

The script generates a CSV file named "LicensedSharedMailboxesReport_" followed by the current date and time. Each row in the CSV file represents a licensed shared mailbox and includes information such as display name, user principal name (UPN), mailbox size, litigation hold status, in-place archive status, and assigned licenses.

If no licensed shared mailboxes are found, a message is displayed indicating the absence of such mailboxes. Otherwise, the user is informed about the total number of licensed shared mailboxes, and there is an option to open the output file.

## Additional Resources

For more detailed information about the script's execution, you can refer to the [official documentation](https://o365reports.com/2022/01/19/find-shared-mailboxes-with-license-using-powershell) provided by the O365Reports Team.

## Disclaimer

This script is provided by the O365Reports Team, and users are encouraged to review and understand the script's functionality before execution. Use the script responsibly and ensure compliance with your organization's policies and guidelines.