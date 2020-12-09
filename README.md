# Docker_Installation
Docker-on-Windows-Server-2016

Step1:
Install-WindowsFeature Containers
Retart-Computer -Force
-----------------------------------------
Step2:
1. Open Powershell and check for supported protocols by using
[Net.ServicePointManager]::SecurityProtocol

2. Run the following 2 cmdlets to set .NET Framework strong cryptography registry keys: {to enable tls1,tls1.2 etc..}
Set-ItemProperty -Path 'HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NetFramework\v4.0.30319' -Name 'SchUseStrongCrypto' -Value '1' -Type DWord
Set-ItemProperty -Path 'HKLM:\SOFTWARE\Microsoft\.NetFramework\v4.0.30319' -Name 'SchUseStrongCrypto' -Value '1' -Type DWord

3. Restart Powershell and check again for supported protocol by using 
[Net.ServicePointManager]::SecurityProtocol

 -- --------------------------------------
 Step3:
[Net.ServicePointManager]::SecurityProtocol
Install-PackageProvider Nuget –Force
Install-Module -Name DockerMsftProvider -Force
Get-ExecutionPolicy
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
Install-Package -Name docker -ProviderName DockerMsftProvider -Force
