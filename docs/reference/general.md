# General Reports Reference

Cervantes is a project that uses Handlebars, a popular templating engine, along with HTML to generate and automate reports. Here's a brief overview of how it works:

## Handlebars Syntax

Handlebars uses a simple templating language which allows you to create reusable HTML templates. The main syntax elements include:

- Expressions: These are wrapped in double curly braces `{{ }}`. For example, `{{title}}` would render the value of the `title` property from the provided data. With `{{{ }}}` it would render html content.
    
- Block expressions: These are similar to expressions but also allow for more complex logic. For example, `{{#each items}} {{this}} {{/each}}` would loop over an array of `items` and render each item.

- Helpers: These are functions that can be used within the template. For example, `{{link url text}}` could render a link with the provided `url` and `text`.

## Loop items in Cervantes

Cervantes is using TinyMCE, a rich text editor so it's important to note that it only supports well-formatted HTML. This means that you can't use Handlebars expressions directly in the editor. 
To fix this you can use the `{{#each}}` helper inside an HTML comment  in order to loop over an array of items and render them. 

For example, you can loop the document control like this:

```html

<table>
    
    <tbody>
    
    <tr>
        <th>Document Name</th>
        <th>Document Version</th>
        <th>Document Description</th>
    </tr>
    
    <!--{{#each Documents}} --> 
        <tr>
        <td>{{DocumentName}}</td>
        <td>{{DocumentVersion}}</td>
        <td>{{{DocumentDescription}}}</td>
        </tr>

    <!--{{/each}} -->
    
    </tbody>
    
</table>

```

In this example `<!--{{#each Documents}} -->` and `!--{{/each}} -->` is used to loop over an array of Documents. For each Document in the array, a new table row `<tr>` is created with three cells `<td>`.

## Handlebars Variables Reference

### General

| Variable          | Description       |
|-------------------|-------------------|
| `{{Year}}`        | The current year  |
| `{{Today}}`       | The current date  |
| `{{{PageBreak}}}` | Adds a page break |

### Organization 

| Variable                        | Description                          |
|---------------------------------|--------------------------------------|
| `{{OrganizationName}}`          | The name of the organization.        |
| `{{OrganizationEmail}}`         | The email of the organization.       |
| `{{OrganizationPhone}}`         | The phone of the organization.       |
| `{{{OrganizationDescription}}}` | The description of the organization. |
| `{{OrganizationContactName}}`   | The contact of the organization.     |
| `{{OrganizationUrl}}`           | The url of the organization.         |

### Client

| Variable                     | Description                       |
|------------------------------|-----------------------------------|
| `{{ClientName}}`             | The name of the client.           |
| `{{ClientEmail}}`            | The email of the client.          |
| `{{ClientPhone}}`            | The phone of the client.          |
| `{{{ClientDescription}}}`    | The description of the client.    |
| `{{ClientContactName}}`      | The contact of the client.        |
| `{{ClientUrl}}`              | The url of the client.            |

### Project

| Variable                      | Description                          |
|-------------------------------|--------------------------------------|
| `{{ProjectName}}`             | The name of the project.             |
| `{{{ProjectDescription}}}`    | The description of the project.      |
| `{{StartDate}}`               | The start date of the project.       |
| `{{EndDate}}`                 | The end date of the project.         |
| `{{ProjectLanguage}}`         | The language of the project.         |
| `{{ProjectStatus}}`           | The status of the project.           |
| `{{ProjectType}}`             | The type of the project.             |
| `{{ProjectScore}}`            | The score type of the project.       |
| `{{ProjectExecutiveSummary}}` | The executive summary of the project |


### Project Members

Project Members comes in an array of users. So you need yo use the `<!--{{#each Users}} -->` and `!--{{/each}} -->` to loop over the array.
The following variables are available for each user:

| Variable             | Description                         |
|----------------------|-------------------------------------|
| `{{UserFullName}}`   | The name of the user member.        |
| `{{UserEmail}}`      | The email of the user member.       |
| `{{UserPhone}}`      | The phone of the user member.       |
| `{{{UserDescription}}}` | The description of the user member. |
| `{{UserPosition}}`   | The position of the user member.    |


### Documents

The Document Control comes in an array of Documents. So you need yo use the `<!--{{#each Documents}} -->` and `!--{{/each}} -->` to loop over the array.
The following variables are available for each documents:

| Variable                     | Description                       |
|------------------------------|-----------------------------------|
| `{{DocumentName}}`           | The name of the document.         |
| `{{DocumentVersion}}`        | The version of the document.      |
| `{{{DocumentDescription}}}`  | The description of the document.  |

### Targets

Targets comes in an array. So you need yo use the `<!--{{#each Targets}} -->` and `!--{{/each}} -->` to loop over the array.
The following variables are available for each documents:

| Variable                | Description                    |
|-------------------------|--------------------------------|
| `{{TargetName}}`        | The name of the target.        |
| `{{TargetDescription}}` | The description of the target. |
| `{{TargetType}}`        | The type of the target.        |

### Vulnerabilities

Vulnerabilities comes in an array of vulnerabilities. So you need yo use the `<!--{{#each Vulns}} -->` and `!--{{/each}} -->` to loop over the array.
The following variables are available for each vulnerability:

| Variable                  | Description                                             |
|---------------------------|---------------------------------------------------------|
| `{{VulnName}}`            | The name of the vulnerability.                          |
| `{{VulnLanguage}}`        | The description of the vulnerability.                   |
| `{{VulnFindingId}}`        | The internal finding id of the vulnerability.           |
| `{{VulnCve}}`             | The cve of the vulnerability.                           |
| `{{VulnCwes}}`            | The cwes of the vulnerability.                          |
| `{{{VulnDescription}}}`   | The description of the vulnerability.                   |
| `{{VulnCategory}}`        | The category of the vulnerability.                      |
| `{{VulnRisk}}`            | The risk associated of the vulnerability.               |
| `{{VulnStatus}}`          | The status of the vulnerability.                        |
| `{{{VulnImpact}}}`        | The impact of the vulnerability.                        |
| `{{VulnCvss}}`            | The cvss of the vulnerability.                          |
| `{{VulnCvssVector}}`      | The cvss vector string of the vulnerability.            |
| `{{{VulnRemediation}}}`   | The remediation of the vulnerability.                   |
| `{{VulnComplexity}}`      | The remediation complexity of the vulnerability.        |
| `{{VulnPriority}}`        | The remediation priority of the vulnerability.          |
| `{{VulnJiraCreated}}`     | Boolean if jira ticket is created of the vulnerability. |
| `{{VulnJira}}`            | Jira key of the vulnerability.                          |
| `{{{VulnPoc}}}`           | The poc of the vulnerability.                           |
| `{{VulnOwaspRisk}}`       | The owasp risk of the vulnerability.                    |
| `{{VulnOwaspImpact}}`     | The owasp impact of the vulnerability.                  |
| `{{VulnOwaspLikelihood}}` | The owasp likelihood of the vulnerability.              |
| `{{VulnOwaspVector}}`     | The owasp vector of the vulnerability.                  |
| `{{VulnTargets}}`         | The targets of the vulnerability.                       |

The following variables are available for the total number of vulnerabilities (not inside the vuln array):

| Variable                | Description                                               |
|-------------------------|-----------------------------------------------------------|
| `{{VulnCriticalCount}}` | The number of critical vulnerabilities inside the project |
| `{{VulnHighCount}}`     | The number of high vulnerabilities inside the project     |
| `{{VulnMediumCount}}`   | The number of medium vulnerabilities inside the project   |
| `{{VulnLowCount}}`      | The number of low vulnerabilities inside the project      |
| `{{VulnInfoCount}}`     | The number of info vulnerabilities inside the project     |
| `{{VulnTotalCount}}`    | The total number of vulnerabilities inside the project    |

### Tasks

Tasks comes in an array. So you need yo use the `<!--{{#each Tasks}} -->` and `!--{{/each}} -->` to loop over the array.

The following variables are available for each task:

| Variable                | Description                      |
|-------------------------|----------------------------------|
| `{{TaskName}}`          | The name of the task.            |
| `{{{TaskDescription}}}` | The description of the task.     |
| `{{TaskStatus}}`        | The status of the task.          |
| `{{TaskStartDate}}`     | The start date of the task.      |
| `{{TaskEndDate}}`       | The end date of the task.        |
| `{{TaskAssignedTo}}`      | The assigned user of the task.   |
| `{{TaskCreatedBy}}`      | The user who created the task. |

### Vaults
Vaults comes in an array. So you need yo use the `<!--{{#each Vaults}} -->` and `!--{{/each}} -->` to loop over the array.

The following variables are available for each vault:

| Variable                     | Description                       |
|------------------------------|-----------------------------------|
| `{{VaultName}}`              | The name of the vault.            |
| `{{{VaultDescription}}}`     | The description of the vault.     |
| `{{VaultType}}`              | The type of the vault.            |
| `{{VaultCreatedBy}}`            | The status of the vault.          |
| `{{VaultCreatedDate}}`        | The status of the vault.          |
| `{{VaultValue}}`            | The status of the vault.          |

