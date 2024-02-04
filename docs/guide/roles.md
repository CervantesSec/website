# Roles

Cervantes has four roles included: **Admin**, **SuperUser**, **User** and **Client**. 
Each role has different permissions and access to the application.

## Admin

The **Admin** role has full access to the application.

## SuperUser

The **SuperUser** role has access to the following sections:

- [Home](#)
- [Calendar](calendar.md) : Personal Calendar
- [Knowledge Base](projects.md)
- [Projects](projects.md): Only admin and superuser can create projects and assign members to them and generate the reports.
- [Clients](clients.md): Only admin and superuser can create and edit clients
- [Vulnerabilities](vulns.md): Only admin and superuser can create vulnerabilities and assign them to projects.
- [Documents](documents.md): Only admin and superuser can create and edit documents
- [Tasks](tasks.md)
- [Report Templates](templates.md): Only admin and superuser can create and edit templates
- [Report Components](components.md): Only admin and superuser can create and edit components
- [Workspaces](workspaces.md)
- [Checklists](checklists.md)
- [Targets](targets.md)
- [Vaults](vaults.md)

## User

The **User** role has access to the following sections:

- [Home](#)
- [Calendar](calendar.md) : Personal Calendar
- [Knowledge Base](projects.md)
- [Projects](projects.md): Only admin and superuser can create projects and assign members to them and generate the reports. User can only interact if its added to the project.
- [Clients](clients.md): Only admin and superuser can create and edit clients. User has only read access.
- [Vulnerabilities](vulns.md): Only admin and superuser can create vulnerabilities and assign them to projects.
- [Documents](documents.md): Only admin and superuser can create and edit documents
- [Tasks](tasks.md): User can only interact if its added to the project.
- [Workspaces](workspaces.md)
- [Checklists](checklists.md)
- [Targets](targets.md)
- [Vaults](vaults.md)

## Client

The **Client** role has access to the following sections:

- [Projects](projects.md)
- [Vulnerabilities](vulns.md)