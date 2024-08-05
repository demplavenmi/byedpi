Is the software still visible under list of installed programs in control panel? If so, you could try a third-party uninstaller tool like Revo Uninstaller or Your Uninstaller . Maybe that might remove the remnants of NetExtender.
 
**Download Zip ––– [https://verbbatomi.blogspot.com/?file=2A0Smz](https://verbbatomi.blogspot.com/?file=2A0Smz)**


 
Finally bit the bullet and remove it the old fashion way. Deleted the folder under program files and removed all references to netextender in the registry. I was then able to install the new version of netextender (ver 6) that will work on windows 8.
 
There is an uninst.exe file in the program files directory of older versions (3.5.xxx and earlier). If you copy and run from the program files directory of the computer you want to uninstall, you can remove with any logged in user. Hopefully, Sonicwall will make this process easier now that Dell has acquired them.

Was able to download 3.5 and get the uninstall.exe. Ran it from the install location and that allowed us to update NetExtender to 6.0. Saved us beaucoup time considering all the computers this was happening on. Nice work!
 
Just a heads up, ran into this problem same as listed above, and was able to use the 6.0 version to uninstall. Just had to manually delete the files in C:\Program Files (x86)\SonicWALL\SSL-VPN\NetExtender because it left a couple things. After that the installer worked perfectly.
 
I am wondering what is the best way to uninstall an application. We have several applications installed on machines that are not deployed from Intune, but have been manually installed over the years. Now we would like to remove X number of applications from X number of machines.
 
Take for example Sonicwall Netextender. We have 100 machines with this application, and they have different versions, so that means different locations within registry. What I would like, is a script that would search within add/and remove programs within Control Panel, and say something like, if the application name = SonicWall then silent uninstall and postpone reboot if that is necessary.
 
If you are managing devices using an enterprise client solution like Intune, then the ideal way to uninstall unwanted applications will be to script the removal and set them up as PS and\or Win32 apps. Then to ensure that users are not able to install unapproved apps themselves, downgrade their permissions and enforce elevation controls like cloud laps.
 
In General, Intune mainly focus on the app which are deployed via Intune. For the app which are not deployed via Intune, you can check to see if it can be removed via PowerShell script. Based as I know, some apps can also be uninstalled via Win32. You can check if the app has silently uninstalled command. If yes, then you can try to deploy the package via Intune win32 and assign the user or device group under uninstall assignment to see if the app can be uninstalled.
 
So I am having the exact opposite issue. I was able to get the newer versions to remove, but anything that returned "C:\Program Files\Dell\SupportAssist\uninstaller.exe /arp" as the UninstallString is failing in my automation as I can't get the prompt to not display (I have around 700 agents to remove this crap from, some with multiple versions, so I feel your pain).
 
Ran into a similar problem. I had a bunch of computers all with different versions of Support Assist. I compiled this from a few different sources. So far I have had really good success. I am using PDQ deploy. I am not the most PowerShell proficient but perhaps this will help.
 
This is what I came up with..Uninstalls "Dell SupportAssist" and "Dell SupportAssist OS Recovery Plugin for Dell Update"Hope this helps someone else too.. The code probably could be cleaned up or simplified a bit but it worked for me.
 
This seems odd to me because the user name, password and domain are entered on the NetExtender client. After this error occurs, the only way to connect again is to uninstall, reboot, and reinstall NetExtender. He can connect fine to the Sonicwall SSLVPN demo site, and a different user can connect fine to this site from a different PC. Any clues?
 
I have had some seemingly random success. I would just try and try and eventually it would work. I thought this might be related to time so I checked the config on the firewall and DC and everything was in perfect sync, so I don't think that is the issue.
 
Another possibility I haven't been able to test yet, related to the above, is that the reason is related to the computer trying to connect not being a member of the domain. The workstations I am testing from are not domain joined (to the domain doing the LDAP auth). However, the issue is the same when using a "LocalUser" from the sonicwall device.
 
I tend to use these two techniques to work around the issue of a connection dropping, and upon reconnection, only the "Sent" bytes counter in the SSL-VPN NetExtender client showing traffic while "Received" sits connects with about 600bytes received and just stays on that number.
 
I presume the "reboot" solution works because it cycles whatever cached credentials / ip adddress / auth token that the client isn't releasing, but when you cycle the NIC, it picks up on these changes.
 
Coming back to explain my findings: this turned out to be caused by an old firmware on the Sonicwall device, incompatible with the latest NetExtender client, while the compatible client was incompatible with Windows 7.
 
Chocolatey tracks packages, which are the files in$env:ChocolateyInstall\lib\packagename. These packages may or may notcontain the software (applications/tools) that each package represents.The software may actually be installed in Program Files (most nativeinstallers will install the software there) or elsewhere on themachine.
 
With auto uninstaller turned off, a chocolateyUninstall.ps1 is requiredto perform uninstall from the system. In the absence ofchocolateyUninstall.ps1, choco uninstall only removes the package fromChocolatey but does not remove the software from your system (unlessin the package directory).
 
Synchronizer and AutoUninstaller enhancements in licensedversions of Chocolatey ensure that Autouninstaller is up to 95%effective at removing software without an uninstall script. This isbecause synchronizer ensures the registry snapshot stays up to dateand licensed enhancements have the ability to inspect more locationsto determine how to automatically uninstall software.
 
Options and switches apply to all items passed, so if you arerunning a command like install that allows installing multiplepackages, and you use --version=1.0.0, it is going to look for andtry to install version 1.0.0 of every package passed. So please splitout multiple package calls when wanting to pass specific options.
 
Are you sure a Windows update hasn't happened roughly at the same time? I found myself in the same situation and uninstalling and re-installing WinPcap after a reboot has helped, even without need to uninstall and re-install Wireshark itself.
 
Just to facilitate diagnostic, not suitable as a workaround if it eventually works: does running Wireshark with administrator privileges change the situation, i.e. can you see the interfaces in that case?
 
I hadn't suggested it yet as I was trying to ascertain the particular circumstances, but uninstalling WinPcap and installing npcap has been known to improve things if it's other software (AV or VPN) that's interfering.
 
Occasionally, the fastest way to resolve certain problems with the Agent is to fully remove it from the device and then reinstall it. However, many issues can be traced back to the .NET Framework itself. Therefore, we recommend that you first run a ComStore component on the device to resolve any .NET Framework issues before uninstalling and reinstalling the Agent.
 
During software installation, package managers download and install the main binary package and all the necessary dependencies. Once the application is no longer needed, it is advisable to remove it since its packages take up storage space and may hinder performance.
 
The **apt remove** command uninstalls the application but does not remove configuration files. To clear packages from the system completely, use **apt purge**. The **purge** option deletes packages and removes all dependencies:
 
**Snap** is a popular software package and deployment system designed for application management on Ubuntu. Uninstalling snaps on Ubuntu is straightforward, as the utility packs all the dependencies into a single package.
 
The **snap remove** command completely deletes the software from the system, including config files and all associated user data. For example, remove the Firefox snap by executing the following command:
 
Third-party repositories allow users to access applications that are unavailable in the default system repositories. The **ppa-purge** utility provides a way to uninstall all the packages from a single repository and remove the repository itself.
 
Ubuntu users who prefer managing packages via a graphical interface can use **Ubuntu Software Center**, the default GUI solution. Another popular option is Synaptic Package Manager, which offers more granular control over packages.
 
Many Ubuntu users prefer **Synaptic Package Manager** due to its robust build and feature-rich interface. To uninstall packages using **Synaptic**, launch the tool and follow the steps below:
 
SonicWall NetExtender is a software application that provides users with the ability to securely connect to their corporate networks from remote locations. This is achieved through the creation of a Virtual Private Network (VPN), which encrypts data and ensures secure communication over the internet.
 
The NEIdle.exe file is necessary for the proper functioning of the SonicWall NetExtender software. It is responsible for certain processes that enable t