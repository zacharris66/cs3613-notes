## Install Code via CLI
```bash
curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64' --output vscode.deb

sudo apt install ./vscode.deb
```
## Launch Code Tunnel
```bash
./code tunnel
```

1. Selected "Github Account" for your tunnel login.
2. Visit [https://github.com/login/devices](https://github.com/login/devices) 
3. Login to Github and enter the code given in the CLI
4. Authorize the connection to your Github Account.
5. Return to the CLI and name the machine in the CLI using a descriptive name
6. Visit the given URL in the CLI to verify your setup is working.
## Setup Code Tunnel Server
1. Once you have verified your code tunnel is working we will now setup a background service to run our code tunnel on startup and restart as needed.
2. In your CLI open a new file in nano via:
```bash
sudo nano /etc/systemd/system/code-tunnel.service
```
3. Enter the following into your `code-tunnel.service`, ensuring that you replace the `<user>` tags with the user on your server. (This is the portion before the `@` sign on your prompt.)
```bash
[Unit]
Description=Visual Studio Code Tunnel
After=network.target
StartLimitIntervalSec=0

[Service]
Type=simple
User=<user>
Group=<user>
Restart=always
RestartSec=10
ExecStart=/usr/bin/code "tunnel" "--cli-data-dir" "/home/<user>/.vscode/cli" "--verbose" "service" "internal-run"

[Install]
WantedBy=multi-user.target
```
4. Exit nano (Ctrl+X) ensuring you save the modified file.
5. Enable to service we just created:
```bash
sudo systemctl enable code-tunnel.service
```
6. Start the service we just created:
```bash
sudo systemctl start code-tunnel.service
```
7. Check the status of our service to ensure everything is working correctly:
```bash
sudo systemctl status code-tunnel.service
```
You may need to hit `q` after looking at status to return to the command prompt.
8. Ensure your your code tunnel is working by visiting [vscode.dev](https://vscode.dev) and login to your GitHub to connect to the tunnel. 
	1. Click the Remote Connection Icon in the lower left.
	2. Click `Connect to Tunnel`
	3. Select the box you have selected.
## Ensure Our Service After Reboot
1. Return to your CLI window and execute the command:
```bash
sudo reboot now
```
2. Your Virtual Server will now reboot and return to service. Give it roughly 2-3 minutes to complete.
3. After waiting for the server to reboot see if the VSCode Tunnel is available via the [vscode.dev](https://vscode.dev) link.