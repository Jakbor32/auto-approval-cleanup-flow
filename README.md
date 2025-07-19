## Main purpose flow

The primary goal of this flow is to optimize the operation of systems that utilize Power Automate and SharePoint, specifically by managing and cleaning up Teams approval notifications that remain after a flow has completed its execution. This ensures that users are not left with outdated or unresolved approval messages, improving clarity, system hygiene, and user experience.

<img width="1009" height="820" alt="1" src="https://github.com/user-attachments/assets/fdad6e60-2157-4ad1-8be7-5f9c7a737f9a" />
<img width="1030" height="1548" alt="2" src="https://github.com/user-attachments/assets/d6cff8b5-1909-491d-aa70-fa404a571392" />


## Process diagram

![Diagram](https://github.com/user-attachments/assets/1ee22065-78d6-401c-9590-3a9f58d4ff11)


## Required licenses
- SharePoint
requires a Microsoft 365 license (e.g. E1, E3, or E5).

- Power Automate
Requires a Power Automate Per User or Per Flow Plan to use premium connectors like Invoke HTTP Request.

> ⚠️ **Important:**  
> **Premium connector bellow**
<img width="221" height="61" alt="3" src="https://github.com/user-attachments/assets/23175a53-aaa9-40b6-b5c7-037664d5ae4a" />

### How to configure HTTP Request
<img width="407" height="275" alt="4" src="https://github.com/user-attachments/assets/a55fe340-b4a8-4723-ad5d-24bf83981c5d" />

```
https://approvals.teams.microsoft.com
```

<img width="768" height="345" alt="6" src="https://github.com/user-attachments/assets/e9a64f4a-fe72-41db-9141-65d9f752f311" />    

```
workflow()?['tags']?['environmentName']
```

## Used connectors
- SharePoint – used for reading and updating list items
- HTTP Request (Entra) – used for sending custom requests to external services (premium)
- Teams – used to create and manage approvals in Microsoft Teams
- Outlook – used to send notification emails via Outlook

## Import and configuration
1. Downloading a file from [Releases](https://github.com/Jakbor32/auto-approval-cleanup-flow/releases/tag/flow-package)
   
2. Import zip package to Power Automate
<img width="571" height="184" alt="8" src="https://github.com/user-attachments/assets/df55dc55-1358-4185-9c38-2272b7a8282c" />

3. Configure new connections to connectors
<img width="1629" height="736" alt="9" src="https://github.com/user-attachments/assets/33148a51-d86a-436a-8959-78a671aaaa59" />

4. Set flow Create as new
<img width="514" height="370" alt="10" src="https://github.com/user-attachments/assets/1f856f49-18d2-4df2-aae9-b64abf853564" />

5. After getting errors - errors will be because flow does not have embedded sharepoint/teams links
<img width="1223" height="601" alt="12" src="https://github.com/user-attachments/assets/ea81ae04-a50f-4be4-94cd-9c822831c5bf" />

6. Correct all connection parameters on the flow so that it points to the correct sharepoint
<img width="663" height="279" alt="13" src="https://github.com/user-attachments/assets/9210187c-23d9-43ca-ae33-b0803350ea5c" />



