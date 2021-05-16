## Installing Visual Studio Code in CentOS 7

<p>The standared installation steps for visual studio code is going well with CentOS 8 and with any above releases. However, when you try to do the same steps with CentOS 7, the installation steps will done successfully but the system wont be run.</p>
<p>The problem accured due to the latest of Visual Studio Code dosent support CentOS 7, we need to install a previous version of V.S Code to make the life easy with CentOS 7.</p>
### prerequisites
* A CentOS 7 Machine with installed GUI.
* Putty, of course.

### First lets do some VS configurations:

Importing the Microsoft GPG key
<pre><code>$ sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc</code></pre>

Create the following repo file to enable the Visual Studio Code repository
<pre><code>$ sudo nano /etc/yum.repos.d/vscode.repo</code></pre>

Drop the following lines into the new file
<pre><code>
[code]
name=Visual Studio Code
baseurl=https://packages.microsoft.com/yumrepos/vscode
enabled=1
gpgcheck=1
gpgkey=https://packages.microsoft.com/keys/microsoft.asc
</code></pre>
Save and exit the file

### Second Install VS Code
Its required to select a specific version of visual studio code thats compatible with CntOS 7 
<pre><code>$ sudo yum install code-1.52.1-1608137084.el7.x86_64 </code></pre>

You have to lock the version since if you upgrade it you cannot use it anymore.
<pre><code>
$ sudo yum install yum-plugin-versionlock
$ sudo yum versionlock code
</code></pre>

<p>Thats it ...!</p>
to run tyhe visual studio code, open a new terminal from the machine GUI and hit down this command
<pre><code>$ code </code></pre>
