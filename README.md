# FreeCRT
An SSH Client based on a distributed Client/Server architecture

<h2>How to Use FreeCRT</h2>
<p>FreeCRT can be used in two main ways: as a standalone SSH client or in a distributed server/client model.</p>

<h3>Standalone Mode</h3>
<p>Simply use the <b>Session Manager</b> or the <b>Quick Connect</b> bar to connect to your SSH servers. All connections are managed locally.</p>

<h3>Distributed Mode (SocketProxy)</h3>
<p>This is a core feature of FreeCRT. You can run FreeCRT on one machine (the "server") and access your SSH sessions from FreeCRT in another device (the "client").</p>
<ol>
    <li>On the machine running FreeCRT(the "server"), find the backend WebSocket URL. It is displayed as "Current Backend" in the main window (e.g., <code>ws://192.168.1.5:8888</code>).</li>
    <li>Click the <b>Manage Backend</b> button. In the dialog that opens, you copy the Local Backend Address to clipboard by clicking the <b>Export ws://host:port</b> button.</li>
    <li>On the client device, paste this URL to the client device by clicking the <b>Auto Import ws://host:port from Clipboard</b> button.</li>
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
    <li>All settings(without password) save to HKEY_CURRENT_USER\Software\FreeCRT\SSHClient</li>
<img width="2765" height="454" alt="img" src="https://github.com/user-attachments/assets/3188b93b-2178-421f-bded-7136994c9b12" />
    <li>All session password save to Windows Credential Manager</li>
<img width="1344" height="364" alt="img_1" src="https://github.com/user-attachments/assets/16e29ff0-330c-458f-99db-67d1ce5d0cfd" />
</ul>
