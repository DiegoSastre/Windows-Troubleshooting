# Windows User & Account Support

## Objective

Practice common Windows user and account support tasks performed by an IT Help Desk technician.

This lab focuses on local user account management, group membership, NTFS permissions, and file access verification.

## Scenario

A new employee needs a Windows account and access to a department folder.

As a Help Desk technician, the goal is to create a standard local user account, review group membership, configure folder permissions, and verify that the user has the expected level of access.

## Environment

- Windows 11 Home
- Local Windows accounts
- Command Prompt
- File Explorer
- NTFS file system

## Tools Used

- `whoami`
- `net user`
- `net localgroup`
- `icacls`
- File Explorer

---

## 1. Review Existing User Accounts

The first step is to identify the current Windows user and review the local accounts available on the computer.

### Commands

```cmd
whoami
net user
```

### Evidence

![Existing User Accounts](./screenshots/01-existing-user-accounts.png)

This step helps identify the account currently being used and review the local accounts configured on the computer.

---

## 2. Create a Standard Local User

A dedicated test account is created to simulate onboarding a new employee.

The account is configured as a standard user rather than an administrator, following the principle of least privilege.

### Command

```cmd
net user HelpDesk.Test * /add
```

The asterisk prompts for a password without displaying it in the command itself.

### Evidence

![Create Local User](./screenshots/02-create-local-user.png)

---

## 3. Review User Information and Group Membership

After creating the account, its properties and local group membership are reviewed.

This helps verify that the account exists and has the expected privileges.

### Commands

```cmd
net user HelpDesk.Test
net localgroup Users
net localgroup Administrators
```

### Evidence

![User Group Membership](./screenshots/03-user-group-membership.png)

The account's group membership is checked to confirm that it has standard user privileges and has not been added to the local Administrators group.

---

## 4. Create a Department Folder

A dedicated test directory is created to simulate a department folder containing company resources.

### Command

```cmd
mkdir C:\HelpDesk-Lab\DepartmentFiles
```

A sample file will also be created for access testing.

### Evidence

![Department Folder](./screenshots/04-department-folder.png)

---

## 5. Review and Configure NTFS Permissions

NTFS permissions determine which users and groups can access files and folders, and what actions they can perform.

The existing permissions are reviewed before configuring access for the test account.

### Command

```cmd
icacls "C:\HelpDesk-Lab\DepartmentFiles"
```

### Evidence

![NTFS Permissions](./screenshots/05-ntfs-permissions.png)

The goal is to grant the test user the appropriate access without giving unnecessary permissions.

---

## 6. Validate User Access

The final step is to verify that the test account can access the department folder according to its assigned permissions.

Access is tested using the test account rather than assuming that the permission configuration worked.

### Evidence

![User Access Validation](./screenshots/06-user-access-validation.png)

Successful access validation confirms that the configured permissions work as expected.

---

## Findings

_To be completed after performing the troubleshooting exercises._

## Troubleshooting Relevance

This lab demonstrates common Help Desk responsibilities involving local account creation, group membership verification, NTFS permissions, and file access troubleshooting.

Understanding the relationship between user accounts, security groups, and file permissions helps technicians investigate access-related problems systematically.

## Conclusion

_To be completed after completing the exercises and validating the test account's access._
