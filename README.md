# FreeCRT
An SSH Client based on a distributed Client/Server architecture

## Why FreeCRT?

In many secure corporate environments, direct SSH access (port 22) to servers is disabled in favor of session-managed bastion hosts, such as BeyondTrust PowerBroker. While this enhances security and auditing capabilities, it often forces users into cumbersome web-based terminals or restricted clients, preventing them from using their preferred local SSH clients and tools (e.g., VS Code Remote, rsync, scp).

**`FreeCRT` solves this problem.**

It allows you to use your native SSH client(FreeCRT A) on your local machine to connect to remote servers(FreeCRT B runing in Windows VM). It achieves this by establishing the secure session through the bastion host via a websocket, rather than a direct port 22 connection. This means your session is still fully managed and audited by the bastion host, satisfying security requirements, while you get to keep the productivity and comfort of your local development environment.

<h2>How to Use FreeCRT</h2>
<p>FreeCRT can be used in two main ways: as a standalone SSH client or in a distributed server/client model.</p>

<h3>Standalone Mode</h3>
<p>Simply use the <b>Session Manager</b> or the <b>Quick Connect</b> bar to connect to your SSH servers. All connections are managed locally.</p>

<h3>Distributed Mode (SocketProxy)</h3>
<p>This is a core feature of FreeCRT. You can run FreeCRT on one machine (the "server") and access your SSH sessions from FreeCRT in another device (the "client").</p>
<ol>
    <li>On the machine running FreeCRT(the "server"), find the backend WebSocket URL. It is displayed as "Current Backend" in the main window (e.g., <code>ws://192.168.1.5:8888</code>).</li>
    <img width="2265" height="1020" alt="image" src="https://github.com/user-attachments/assets/4d299e65-a2de-4060-ae92-f23316b39062" />
    <li>Click the <b>Manage Backend</b> button. In the dialog that opens, you copy the Local Backend Address to clipboard by clicking the <b>Export ws://host:port</b> button.</li>
    <img width="434" height="359" alt="image" src="https://github.com/user-attachments/assets/e66424ed-5d3b-453d-8956-d33a99131ab2" />
    <li>On the client device, paste this URL to the client device by clicking the <b>Auto Import ws://host:port from Clipboard</b> button.</li>
    <img width="420" height="368" alt="image" src="https://github.com/user-attachments/assets/1eb48fd2-b259-4d42-9061-ab8f0a99d6ab" />
    <li>Now you can close Manage Backend dialog and open a session using Distributed Mode.</li>
</ol>

<h3>Other Features</h3>
<ul>
    <li><b>SFTP Browser:</b> Open an SFTP file browser for the current session via the "SFTP" button or menu. You can choose different connection modes (Direct, TCP Forward, WebSocket Proxy). For distributed mode, <b>WebSocket Proxy</b> is recommended.</li>
    <li><b>Command Broadcast:</b> Use the bar at the bottom to send a command to all active terminal sessions simultaneously.</li>
    <li><b>Tab Management:</b> Double-click a tab to duplicate the session. Middle-click to close it. Right-click for more options.</li>
</ul>

<h3>Data security</h3>
<ul>
    <li>All settings(without password) save to Windows Registry---HKEY_CURRENT_USER\Software\FreeCRT\SSHClient</li>
<img width="2765" height="454" alt="img" src="https://github.com/user-attachments/assets/3188b93b-2178-421f-bded-7136994c9b12" />
    <li>All sessions password save to Windows Credential Manager</li>
<img width="2246" height="474" alt="image" src="https://github.com/user-attachments/assets/4560e97d-fb20-4177-ba98-c2a442703f01" />
</ul>

<h3>PS: The program is constantly iterating</h3>
<ul>
<li>1.SFTP functionality needs enhancement; currently, only upload and download modules are available.</li>
<li>2.SSH key login is under development.</li>
<li>Due to limited energy, I have discarded some of the less commonly used ssh functions. If you need them, please provide them in the issue area and I will consider adding them.</li>
</ul>
