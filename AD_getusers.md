To gather usernames from Active Directory (AD) and create a CSV file that you can then use to reset passwords, you can use PowerShell. This approach is helpful if you want to perform bulk operations, like resetting passwords for a specific group of users or for all users in a certain organizational unit (OU).

### Step-by-Step Guide to Export Usernames from Active Directory

Here’s how you can export a list of usernames from AD to a CSV file using PowerShell:

#### 1. Open PowerShell with Administrative Privileges
Ensure that you run PowerShell as an administrator to have the necessary permissions to query Active Directory.

#### 2. Load the Active Directory Module
Before you can run any Active Directory commands, you'll need to load the AD module. Enter the following command:

```powershell
Import-Module ActiveDirectory
```

#### 3. Gather User Information
You can use the `Get-ADUser` cmdlet to retrieve user information. Depending on your needs, you might want to filter or select specific users based on criteria such as being in a specific OU or having certain attributes. Here’s a basic example to get started:

```powershell
# Get all users in the domain
$users = Get-ADUser -Filter * -Property SamAccountName

# If you need to get users from a specific OU, use:
# $users = Get-ADUser -Filter * -SearchBase "OU=Users,DC=example,DC=com" -Property SamAccountName
```

#### 4. Export Usernames to a CSV File
Once you have a list of users, you can export their usernames to a CSV file. Modify the path to where you want the CSV file saved:

```powershell
$users | Select-Object SamAccountName | Export-Csv -Path "C:\path\to\usernames.csv" -NoTypeInformation
```

### Optional Adjustments
- **Adding Additional Columns**: If you want to include more details in the CSV file, such as email addresses or full names, you can add those properties in the `Select-Object` cmdlet. For example:

```powershell
$users | Select-Object SamAccountName, Name, EmailAddress | Export-Csv -Path "C:\path\to\usernames.csv" -NoTypeInformation
```

- **Filtering Users**: You can apply filters to select specific users based on various criteria using the `-Filter` parameter in the `Get-ADUser` cmdlet. For example, to get only enabled users:

```powershell
$users = Get-ADUser -Filter 'Enabled -eq $true' -Property SamAccountName
```

### Running the Script
After preparing your script with the appropriate paths and filters:
- Execute the script in your PowerShell session.
- Check the output CSV file to ensure it contains the data you expect.

This method provides a straightforward way to collect usernames from Active Directory, which you can then use for various administrative tasks, including bulk password resets.
