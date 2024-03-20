# OWASP MASTG Report Reference

## Variables Reference

### General

| Variable          | Description      |
|-------------------|------------------|
| `{{Year}}`        | The current year |
| `{{CreatedDate}}` |                  |


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

### Targets

| Variable                | Description                    |
|-------------------------|--------------------------------|
| `{{TargetName}}`        | The name of the target.        |
| `{{TargetDescription}}` | The description of the target. |
| `{{TargetType}}`        | The type of the target.        |

### Android

#### Storage

| Storage         | Test                                                                                  | Status                | Notes               |
|-----------------|---------------------------------------------------------------------------------------|-----------------------|---------------------|
| MASVS-STORAGE-1 | The app securely stores sensitive data.                                               | `{{Storage1Status}}`  | `{{Storage1Note}}`  |
|                 | Testing Local Storage for Sensitive Data                                              | `{{Storage1Status1}}` | `{{Storage1Note1}}` |
|                 | Testing the Device-Access-Security Policy                                             | `{{Storage1Status2}}` | `{{Storage1Note2}}` |
| MASVS-STORAGE-2 | The app prevents leakage of sensitive data.                                           | `{{Storage2Status}}`  | `{{Storage2Note}}`  |
|                 | Testing Memory for Sensitive Data                                                     | `{{Storage2Status1}}` | `{{Storage2Note1}}` |
|                 | Testing Backups for Sensitive Data                                                    | `{{Storage2Status2}}` | `{{Storage2Note2}}` |
|                 | Testing Logs for Sensitive Data                                                       | `{{Storage2Status3}}` | `{{Storage2Note3}}` |
|                 | Determining Whether Sensitive Data Is Shared with Third Parties via Notifications     | `{{Storage2Status4}}` | `{{Storage2Note4}}` |
|                 | Determining Whether the Keyboard Cache Is Disabled for Text Input Fields              | `{{Storage2Status5}}` | `{{Storage2Note5}}` |
|                 | Determining Whether Sensitive Data Is Shared with Third Parties via Embedded Services | `{{Storage2Status6}}` | `{{Storage2Note6}}` |



#### Cryptography

| Crypthography  | Test                                                                                          | Status               | Notes              |
|----------------|-----------------------------------------------------------------------------------------------|----------------------|--------------------|
| MASVS-CRYPTO-1 | The app employs current strong cryptography and uses it according to industry best practices. | `{{Crypto1Status}}`  | `{{Crypto1Note}}`  |
|                | Testing Symmetric Cryptography                                                                | `{{Crypto1Status1}}` | `{{Crypto1Note1}}` |
|                | Testing Random Number Generation                                                              | `{{Crypto1Status2}}` | `{{Crypto1Note2}}` |
|                | Testing the Configuration of Cryptographic Standard Algorithms                                | `{{Crypto1Status3}}` | `{{Crypto1Note3}}` |
| MASVS-CRYPTO-2 | The app performs key management according to industry best practices.                         | `{{Crypto2Status}}`  | `{{Crypto2Note}}`  |
|                | Testing the Purposes of Keys                                                                  | `{{Crypto2Status1}}` | `{{Crypto2Note1}}` |

#### Authentication and Authorization


| Authentication & Authorization | Test                                                                                                    | Status             | Notes            |
|--------------------------------|---------------------------------------------------------------------------------------------------------|--------------------|------------------|
| MASVS-AUTH-1                   | The app uses secure authentication and authorization protocols and follows the relevant best practices. | `{{Auth1Status}}`  | `{{Auth1Note}}`  |
| MASVS-AUTH-2                   | The app performs local authentication securely according to the platform best practices.                | `{{Auth2Status}}`  | `{{Auth2Note}}`  |
|                                | Testing Confirm Credentials                                                                             | `{{Auth2Status1}}` | `{{Auth2Note1}}` |
|                                | Testing Biometric Authentication                                                                        | `{{Auth2Status2}}` | `{{Auth2Note2}}` |
| MASVS-AUTH-3                   | The app secures sensitive operations with additional authentication.                                    | `{{Auth3Status}}`  | `{{Auth3Note}}`  |

#### Network Communications


| Network Communications | Test                                                                                      | Status                | Notes               |
|------------------------|-------------------------------------------------------------------------------------------|-----------------------|---------------------|
| MASVS-NETWORK-1        | The app performs identity pinning for all remote endpoints under the developer's control. | `{{Network1Status}}`  | `{{Network1Note}}`  |
|                        | Testing the Security Provider                                                             | `{{Network1Status1}}` | `{{Network1Note1}}` |
|                        | Testing Data Encryption on the Network                                                    | `{{Network1Status2}}` | `{{Network1Note2}}` |
|                        | Testing the TLS Settings                                                                  | `{{Network1Status3}}` | `{{Network1Note3}}` |
|                        | Testing Endpoint Identify Verification                                                    | `{{Network1Status4}}` | `{{Network1Note4}}` |
| MASVS-NETWORK-2        | The app performs identity pinning for all remote endpoints under the developer's control. | `{{Network2Status}}`  | `{{Network2Note}}`  |
|                        | Testing Custom Certificate Stores and Certificate Pinning                                 | `{{Network2Status1}}` | `{{Network2Note1}}` |

#### Platform Interaction


| Platform Interaction | Test                                                                          | Status                 | Notes                |
|----------------------|-------------------------------------------------------------------------------|------------------------|----------------------|
| MASVS-PLATFORM-1     | The app uses IPC mechanisms securely.                                         | `{{Platform1Status}}`  | `{{Platform1Note}}`  |
|                      | Testing for App Permissions                                                   | `{{Platform1Status1}}` | `{{Platform1Note1}}` |
|                      | Testing for Sensitive Functionality Exposure Through IPC                      | `{{Platform1Status2}}` | `{{Platform1Note2}}` |
|                      | Testing Deep Links                                                            | `{{Platform1Status3}}` | `{{Platform1Note3}}` |
|                      | Testing for Vulnerable Implementation of PendingIntent                        | `{{Platform1Status4}}` | `{{Platform1Note4}}` |
|                      | Determining Whether Sensitive Stored Data Has Been Exposed via IPC Mechanisms | `{{Platform1Status5}}` | `{{Platform1Note5}}` |
| MASVS-PLATFORM-2     | The app uses WebViews securely.                                               | `{{Platform2Status}}`  | `{{Platform2Note}}`  |
|                      | Testing WebView Protocol Handlers                                             | `{{Platform2Status1}}` | `{{Platform2Note1}}` |
|                      | Testing JavaScript Execution in WebViews                                      | `{{Platform2Status2}}` | `{{Platform2Note2}}` |
|                      | Testing WebViews Cleanup                                                      | `{{Platform2Status3}}` | `{{Platform2Note3}}` |
|                      | Testing for Java Objects Exposed Through WebViews                             | `{{Platform2Status4}}` | `{{Platform2Note4}}` |
| MASVS-PLATFORM-3     | The app uses the user interface securely.                                     | `{{Platform3Status}}`  | `{{Platform3Note}}`  |
|                      | Checking for Sensitive Data Disclosure Through the User Interface             | `{{Platform3Status1}}` | `{{Platform3Note1}}` |
|                      | Finding Sensitive Information in Auto-Generated Screenshots                   | `{{Platform3Status2}}` | `{{Platform3Note2}}` |
|                      | Testing for Overlay Attacks                                                   | `{{Platform3Status3}}` | `{{Platform3Note3}}` |

#### Code Quality


| Code Quality | Test                                                                 | Status             | Notes            |
|--------------|----------------------------------------------------------------------|--------------------|------------------|
| MASVS-CODE-1 | The app requires an up-to-date platform version.                     | `{{Code1Status}}`  | `{{Code1Note}}`  |
| MASVS-CODE-2 | The app has a mechanism for enforcing app updates.                   | `{{Code2Status}}`  | `{{Code2Note}}`  |
|              | Testing Enforced Updating                                            | `{{Code2Status1}}` | `{{Code2Note1}}` |
| MASVS-CODE-3 | The app only uses software components without known vulnerabilities. | `{{Code3Status}}`  | `{{Code3Note}}`  |
|              | Checking for Weaknesses in Third Party Libraries                     | `{{Code3Status1}}` | `{{Code3Note1}}` |
| MASVS-CODE-4 | The app only uses software components without known vulnerabilities. | `{{Code4Status}}`  | `{{Code4Note}}`  |
|              | Testing Object Persistence                                           | `{{Code4Status1}}` | `{{Code4Note1}}` |
|              | Make Sure That Free Security Features Are Activated                  | `{{Code4Status2}}` | `{{Code4Note2}}` |
|              | Testing Local Storage for Input Validation                           | `{{Code4Status3}}` | `{{Code4Note3}}` |
|              | Testing for Injection Flaws                                          | `{{Code4Status4}}` | `{{Code4Note4}}` |
|              | Testing for URL Loading in WebViews                                  | `{{Code4Status5}}` | `{{Code4Note5}}` |
|              | Memory Corruption Bugs                                               | `{{Code4Status6}}` | `{{Code4Note6}}` |
|              | Testing Implicit Intents                                             | `{{Code4Status7}}` | `{{Code4Note7}}` |

#### Resilience Against Reverse Engineering


| Resilience against reverse | Test                                                 | Status                   | Notes                  |
|----------------------------|------------------------------------------------------|--------------------------|------------------------|
| MASVS-RESILIENCE-1         | The app validates the integrity of the platform.     | `{{Resilience1Status}}`  | `{{Resilience1Note}}`  |
|                            | Testing Emulator Detection                           | `{{Resilience1Status1}}` | `{{Resilience1Note1}}` |
|                            | Testing Root Detection                               | `{{Resilience1Status2}}` | `{{Resilience1Note2}}` |
| MASVS-RESILIENCE-2         | The app implements anti-tampering mechanisms.        | `{{Resilience2Status}}`  | `{{Resilience2Note}}`  |
|                            | Testing Runtime Integrity Checks                     | `{{Resilience2Status1}}` | `{{Resilience2Note1}}` |
|                            | Testing File Integrity Checks                        | `{{Resilience2Status2}}` | `{{Resilience2Note2}}` |
|                            | Making Sure that the App is Properly Signed          | `{{Resilience2Status3}}` | `{{Resilience2Note3}}` |
| MASVS-RESILIENCE-3         | The app implements anti-static analysis mechanisms.  | `{{Resilience3Status}}`  | `{{Resilience3Note}}`  |
|                            | Testing for Debugging Symbols                        | `{{Resilience3Status1}}` | `{{Resilience3Note1}}` |
|                            | Testing Obfuscation                                  | `{{Resilience3Status2}}` | `{{Resilience3Note2}}` |
|                            | Testing for Debugging Code and Verbose Error Logging | `{{Resilience3Status3}}` | `{{Resilience3Note3}}` |
| MASVS-RESILIENCE-4         | The app implements anti-dynamic analysis techniques. | `{{Resilience4Status}}`  | `{{Resilience4Note}}`  |
|                            | Testing Anti-Debugging Detection                     | `{{Resilience4Status1}}` | `{{Resilience4Note1}}` |
|                            | Testing whether the App is Debuggable                | `{{Resilience4Status2}}` | `{{Resilience4Note2}}` |
|                            | Testing Reverse Engineering Tools Detection          | `{{Resilience4Status3}}` | `{{Resilience4Note3}}` |

### iOS

#### Storage


| Storage         | Test                                                            | Status                 | Notes                |
|-----------------|-----------------------------------------------------------------|------------------------|----------------------|
| MASVS-STORAGE-1 | The app securely stores sensitive data.                         | `{{Storage1Status}}`   | `{{Storage1Note}}`   |
|                 | Testing Local Storage for Sensitive Data                        | `{{Storage1Status3}}`  | `{{Storage1Note3}}`  |
| MASVS-STORAGE-2 | The app prevents leakage of sensitive data.                     | `{{Storage2Status}}`   | `{{Storage2Note}}`   |
|                 | Finding Sensitive Data in the Keyboard Cache                    | `{{Storage2Status7}}`  | `{{Storage2Note7}}`  |
|                 | Testing Backups for Sensitive Data                              | `{{Storage2Status8}}`  | `{{Storage2Note8}}`  |
|                 | Checking Logs for Sensitive Data                                | `{{Storage2Status9}}`  | `{{Storage2Note9}}`  |
|                 | Determining Whether Sensitive Data Is Shared with Third Parties | `{{Storage2Status10}}` | `{{Storage2Note10}}` |
|                 | Testing Memory for Sensitive Data                               | `{{Storage2Status11}}` | `{{Storage2Note11}}` |


#### Cryptography

| Crypthography  | Test                                                                                          | Status               | Notes              |
|----------------|-----------------------------------------------------------------------------------------------|----------------------|--------------------|
| MASVS-CRYPTO-1 | The app employs current strong cryptography and uses it according to industry best practices. | `{{Crypto1Status}}`  | `{{Crypto1Note}}`  |
|                | Verifying the Configuration of Cryptographic Standard Algorithms                              | `{{Crypto1Status4}}` | `{{Crypto1Note4}}` |
|                | Testing Random Number Generation                                                              | `{{Crypto1Status5}}` | `{{Crypto1Note5}}` |
| MASVS-CRYPTO-2 | The app performs key management according to industry best practices.                         | `{{Crypto2Status}}`  | `{{Crypto2Note}}`  |
|                | Testing Key Management                                                                        | `{{Crypto2Status2}}` | `{{Crypto2Note2}}` |

#### Authentication and Authorization

| Authentication & Authorization | Test                                                                                                    | Status             | Notes            |
|--------------------------------|---------------------------------------------------------------------------------------------------------|--------------------|------------------|
| MASVS-AUTH-1                   | The app uses secure authentication and authorization protocols and follows the relevant best practices. | `{{Auth1Status}}`  | `{{Auth1Note}}`  |
| MASVS-AUTH-2                   | The app performs local authentication securely according to the platform best practices.                | `{{Auth2Status}}`  | `{{Auth2Note}}`  |
|                                | Testing Local Authentication                                                                            | `{{Auth2Status3}}` | `{{Auth2Note3}}` |
| MASVS-AUTH-3                   | The app secures sensitive operations with additional authentication.                                    | `{{Auth3Status}}`  | `{{Auth3Note}}`  |

#### Network Communications

| Network Communications | Test                                                                                      | Status                | Notes               |
|------------------------|-------------------------------------------------------------------------------------------|-----------------------|---------------------|
| MASVS-NETWORK-1        | The app secures all network traffic according to the current best practices.              | `{{Network1Status}}`  | `{{Network1Note}}`  |
|                        | Testing Endpoint Identity Verification                                                    | `{{Network1Status5}}` | `{{Network1Note5}}` |
|                        | Testing the TLS Settings                                                                  | `{{Network1Status6}}` | `{{Network1Note6}}` |
|                        | Testing Data Encryption on the Network                                                    | `{{Network1Status7}}` | `{{Network1Note7}}` |
| MASVS-NETWORK-2        | The app performs identity pinning for all remote endpoints under the developer's control. | `{{Network2Status}}`  | `{{Network2Note}}`  |
|                        | Testing Custom Certificate Stores and Certificate Pinning                                 | `{{Network2Status2}}` | `{{Network2Note2}}` |

#### Platform Interaction

| Platform Interaction | Test                                                             | Status                  | Notes                 |
|----------------------|------------------------------------------------------------------|-------------------------|-----------------------|
| MASVS-PLATFORM-1     | The app uses IPC mechanisms securely.                            | `{{Platform1Status}}`   | `{{Platform1Note}}`   |
|                      | Testing UIActivity Sharing                                       | `{{Platform1Status6}}`  | `{{Platform1Note6}}`  |
|                      | Testing App Permissions                                          | `{{Platform1Status7}}`  | `{{Platform1Note7}}`  |
|                      | Testing Universal Links                                          | `{{Platform1Status8}}`  | `{{Platform1Note8}}`  |
|                      | Determining Whether Sensitive Data Is Exposed via IPC Mechanisms | `{{Platform1Status9}}`  | `{{Platform1Note9}}`  |
|                      | Testing Custom URL Schemes                                       | `{{Platform1Status10}}` | `{{Platform1Note10}}` |
|                      | Testing for Sensitive Functionality Exposure Through IPC         | `{{Platform1Status11}}` | `{{Platform1Note11}}` |
|                      | Testing App Extensions                                           | `{{Platform1Status12}}` | `{{Platform1Note12}}` |
|                      | Testing UIPasteboard                                             | `{{Platform1Status13}}` | `{{Platform1Note13}}` |
| MASVS-PLATFORM-2     | The app uses WebViews securely.                                  | `{{Platform2Status}}`   | `{{Platform2Note}}`   |
|                      | Testing iOS WebViews                                             | `{{Platform2Status5}}`  | `{{Platform2Note5}}`  |
|                      | Determining Whether Native Methods Are Exposed Through WebViews  | `{{Platform2Status6}}`  | `{{Platform2Note6}}`  |
|                      | Testing WebView Protocol Handlers                                | `{{Platform2Status7}}`  | `{{Platform2Note7}}`  |
| MASVS-PLATFORM-3     | The app uses the user interface securely.                        | `{{Platform3Status}}`   | `{{Platform3Note}}`   |
|                      | Testing Auto-Generated Screenshots for Sensitive Information     | `{{Platform3Status4}}`  | `{{Platform3Note4}}`  |
|                      | Checking for Sensitive Data Disclosed Through the User Interface | `{{Platform3Status5}}`  | `{{Platform3Note5}}`  |

#### Code Quality

| Code Quality | Test                                                                 | Status              | Notes             |
|--------------|----------------------------------------------------------------------|---------------------|-------------------|
| MASVS-CODE-1 | The app requires an up-to-date platform version.                     | `{{Code1Status}}`   | `{{Code1Note}}`   |
| MASVS-CODE-2 | The app has a mechanism for enforcing app updates.                   | `{{Code2Status}}`   | `{{Code2Note}}`   |
|              | Testing Enforced Updating                                            | `{{Code2Status2}}`  | `{{Code2Note2}}`  |
| MASVS-CODE-3 | The app only uses software components without known vulnerabilities. | `{{Code3Status}}`   | `{{Code3Note}}`   |
|              | Checking for Weaknesses in Third Party Libraries                     | `{{Code3Status2}}`  | `{{Code3Note2}}`  |
| MASVS-CODE-4 | The app only uses software components without known vulnerabilities. | `{{Code4Status}}`   | `{{Code4Note}}`   |
|              | Testing Object Persistence                                           | `{{Code4Status8}}`  | `{{Code4Note8}}`  |
|              | Make Sure That Free Security Features Are Activated                  | `{{Code4Status9}}`  | `{{Code4Note9}}`  |
|              | Memory Corruption Bugs                                               | `{{Code4Status10}}` | `{{Code4Note10}}` |

#### Resilience Against Reverse Engineering


| Resilience against reverse | Name                                                 | Status                   | Notes                  |
|----------------------------|------------------------------------------------------|--------------------------|------------------------|
| MASVS-RESILIENCE-1         | The app validates the integrity of the platform.     | `{{Resilience1Status}}`  | `{{Resilience1Note}}`  |
|                            | Testing Emulator Detection                           | `{{Resilience1Status3}}` | `{{Resilience1Note3}}` |
|                            | Testing Jailbreak Detection                          | `{{Resilience1Status4}}` | `{{Resilience1Note4}}` |
| MASVS-RESILIENCE-2         | The app implements anti-tampering mechanisms.        | `{{Resilience2Status}}`  | `{{Resilience2Note}}`  |
|                            | Making Sure that the App Is Properly Signed          | `{{Resilience2Status4}}` | `{{Resilience2Note4}}` |
|                            | Testing File Integrity Checks                        | `{{Resilience2Status5}}` | `{{Resilience2Note5}}` |
| MASVS-RESILIENCE-3         | The app implements anti-static analysis mechanisms.  | `{{Resilience3Status}}`  | `{{Resilience3Note}}`  |
|                            | Testing for Debugging Symbols                        | `{{Resilience3Status4}}` | `{{Resilience3Note4}}` |
|                            | Testing Obfuscation                                  | `{{Resilience3Status5}}` | `{{Resilience3Note5}}` |
|                            | Testing for Debugging Code and Verbose Error Logging | `{{Resilience3Status6}}` | `{{Resilience3Note6}}` |
| MASVS-RESILIENCE-4         | The app implements anti-dynamic analysis techniques. | `{{Resilience4Status}}`  | `{{Resilience4Note}}`  |
|                            | Testing Reverse Engineering Tools Detection          | `{{Resilience4Status4}}` | `{{Resilience4Note4}}` |
|                            | Testing whether the App is Debuggable                | `{{Resilience4Status5}}` | `{{Resilience4Note5}}` |
|                            | Testing Anti-Debugging Detection                     | `{{Resilience4Status6}}` | `{{Resilience4Note6}}` |

