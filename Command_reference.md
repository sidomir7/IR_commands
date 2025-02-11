| Command | Description |
|---------|-------------|
| Date | Check local time of computer, visually in right corner and in console with command |
| whoami | show current user |
| systeminfo | Get basic info about system |
| Get-HotFix | List installed windows updates with install date |
| set | In CMD list system variables |
| dir ENV: | same as set command but it will work in powershell |
| $env:path -split ";" | formatted list of path values, command above will not show all values if they are long |
| winget list | list installed programs, if available show versions |
| ipconfig /all | show network communication, Ethernet adapters, vpn tunnels etc. |
| netstat -naob | command will show network connections, with b flag shows pid and processes. Good information when analyzing memory |
| netstat -rn | show local DNS cache |
| arp -a | show ARP cache, arp cache is volatile and this information is really hard to obtain without this command |
| net use | show what shares from local network are mounted on local PC |
| net session | displays information about all sessions with the local computer. |
| net share | displays information about all of the resources that are shared on the local computer with network |
| nbtstat -s | Displays NetBIOS client and server sessions, attempting to convert the destination IP address to a name. |
| netsh firewall show config | shows local firewall configuration |
| netsh advfirewall show currentprofile | show firewall rules and state |
| query user, query session | logged in users |
| wmic process get Name,ProcessId,ParentProcessId,CommandLine | list process with name,pid,ppid and command line argument |
| Get-NetTCPConnection | This command will list all processes with network connection and will show CMD line of process as well |
| tasklist /svc | map running processes to services |
| sc query | run it in CMD ! |
| net user | show local users |
| Get-LocalUser | show local user and if it is enabled or not |
| net localgroup "Administrators" | show member of local group with name Administrators |
| wmic startup list | list AutoStart applications |
| Get-CimInstance Win32_StartupCommand | Similar to tasklist /svc but output is better formatted |
| schtasks | list scheduled tasks |
| autorunsc64.exe -a * -s -c -h > autorunsc_output.txt | From sysinternals command line to check lot of possible persistence |
| rsop /v | can save group policy from domain joined PC. GUI will be open and need to be clicked on Files -> Save As |
| gpresult /V | same as rsop /v but without GUI and it can be redirected to output to file |
| Checking windows Logs via Event Viewer | Check system, security, application logs |
| RAM acquisition if it not VM and snapshot can not be done before Investigation. |  |
| Unplugged from network if not done priory |  |
| Image/Triage machine | Commands reference for IR |
