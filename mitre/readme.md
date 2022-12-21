<h1 align="center">MITRE ATT&amp;CK</h1>
<p align="center">This page is about cybersecurity</p>

See more:

https://attack.mitre.org/

https://portswigger.net/web-security

https://www.hackthebox.com/

https://tryhackme.com/

https://www.youtube.com/watch?v=FSjOrIHun-A

# Advanced persistent threat (APT)
_"An advanced persistent threat (APT) is a sophisticated, sustained cyberattack in which an intruder establishes an undetected presence in a network in order to steal sensitive data over a prolonged period of time"_.

## Disable or Remove Feature or Program
https://attack.mitre.org/mitigations/M1042/

### Command and Scripting Interpreter (T1059)
#### PowerShell (001)

* If you want to stop and disable the WinRM for security reasons, you can do so in the Services snap-in (type "services" in the start menu), or you can use PowerShell:

  ```shell 
  Stop-Service WinRM -PassThruSet-Service WinRM -StartupType Disabled -PassThru
  ```
  
  * For test:
  
  ```shell
  Test-WSMan localhost
  ``` 
#### Visual Basic (005)

[Behavior Prevention on Endpoint - M1040](https://attack.mitre.org/mitigations/M1040/)

* Enable Attack Surface Reduction (ASR)
  * [Overview-attack-surface-reduction](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction?view=o365-worldwide)
    * [Microsoft-defender-application-guard](https://learn.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
    
### Remote Service Session Hijacking (T1563)
#### Disable or Remove Feature or Program (M1042)
* Open Control Panel.
* Click on System and Security.
* Under the "System" section, click the "Allow remote access" option.
* Click the "Remote" tab.
* Under the "Remote Assistance" section, clear the "Allow Remote Assistance connection to this computer" option.
* Click the "Apply" button.

### Abuse Elevation Control Mechanism: Bypass User Account Control (T1548/002)
* Type "UAC" on search bar;
* Use the highest enforcement level for UAC

### Microsoft Defender Application Guard

_For Microsoft Edge, Application Guard helps to isolate enterprise-defined untrusted sites, protecting your company while your employees browse the Internet. As an enterprise administrator, you define what is among trusted web sites, cloud resources, and internal networks. Everything not on your list is considered untrusted. If an employee goes to an untrusted site through either Microsoft Edge or Internet Explorer, Microsoft Edge opens the site in an isolated Hyper-V-enabled container._

* https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction?view=o365-worldwide
* https://learn.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard
  * Windows > "Editor de política de grupo"




