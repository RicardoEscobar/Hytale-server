# To update Hytale server in Linux mint
`~/Hytale/hytale-downloader-linux-amd64` is the path to the Hytale downloader executable.
```bash
~/Hytale/hytale-downloader-linux-amd64
```
This will download and update the Hytale server to the latest version.

## Example command to update Hytale server in Linux Mint
```bash
ricardo@OptiPlex-3070:~$ ~/Hytale/hytale-downloader-linux-amd64
downloading latest ("release" patchline) to "2026.01.17-4b0f30090.zip"
[==================================================] 100.0% (1.4 GB / 1.4 GB)B)
validating checksum...
successfully downloaded "release" patchline (version 2026.01.17-4b0f30090)
```
After that, stop the Hytale server if it's running.

# Update Hytale server files in Linux Mint
`~/Hytale/2026.01.17-4b0f30090.zip` is the path to the downloaded Hytale server zip file and `~/Hytale/ServerRicky/` is the path to the Hytale server folder.
Then unzip the downloaded file to update the server files:
```bash
unzip -o ~/Hytale/2026.01.17-4b0f30090.zip -d ~/Hytale/ServerRicky/
```
Or just unzip from `2026.01.17-4b0f30090.zip` the files `HytaleServer.jar`, `HytaleServer.aot`, and `Assets.zip` directly to the Server folder `~/Hytale/ServerRicky/`:

```bash
unzip -o ~/Hytale/2026.01.17-4b0f30090.zip "Server/HytaleServer.jar" "Server/HytaleServer.aot" "Assets.zip" -d ~/Hytale/ServerRicky/
```

# Check the Hytale server version in Linux Mint
`~/Hytale/Server/HytaleServer.jar` is the path to the Hytale server jar file.
To check the Hytale server version in Linux Mint, use the following command in your terminal:
```bash
java -jar ~/Hytale/Server/HytaleServer.jar --version
```
## Example command to check the Hytale server version in Linux Mint
```bash
ricardo@OptiPlex-3070:~$ ~/Hytale/hytale-downloader-linux-amd64 -print-version
2026.01.15-c04fdfe10
```
# Start Hytale server in Linux Mint
`~/Hytale/Server/HytaleServer.jar` is the path to the Hytale server jar file and `~/Hytale/Assets.zip` is the path to the assets zip file.
To start the Hytale server in Linux Mint, use the following command in your terminal:
```bash
java -jar ~/Hytale/Server/HytaleServer.jar --assets ~/Hytale/Assets.zip
```

# Start Hytale server in Linux Mint as a background process
To start the Hytale server in Linux Mint as a background process, use the following command in your terminal:
```bash
nohup java -jar ~/Hytale/Server/HytaleServer.jar --assets ~/Hytale/Assets.zip > hytale_server.log 2>&1 &
```

# Kill Hytale server in Linux Mint if running as a background process
To kill the Hytale server in Linux Mint if running as a background process, use the following command in your terminal:
```bash
pgrep -af HytaleServer.jar
```
This command will list the process ID (PID) of the Hytale server. You will see an output similar to this:
```bash
12345 java -jar /home/ricardo/Hytale/Server/HytaleServer.jar --assets ...
```
Where `12345` is the PID of the Hytale server process.
Use the PID to kill the process:
```bash
kill <PID>
```

# Making the authentication happen automatically in Linux Mint
To make the authentication happen automatically in Linux Mint, you can create a configuration file with your credentials.
First, run the server with:
```bash
java -jar ~/Hytale/Server/HytaleServer.jar --assets ~/Hytale/Assets.zip
```
Then when asques to authenticate:
```bash
/auth login device
```
This will generate a link to authenticate your device. Open the link in your browser and follow the instructions to complete the authentication process.
After completing the authentication, if multiple profiles are available, select the desired profile by running:
```bash
/auth select <profile_number>
```
To avoid authenticating every time you start the server:
```bash
/auth persistence Encrypted
```

# Run playit.gg client in Linux Mint
First, install tmux if you don't have it already. Then, start a new tmux session and run the playit.gg client inside it.
```bash
sudo apt install tmux
tmux new -s playit
playit
```
Now you can detach from the tmux session by pressing `Ctrl + B`, then `D`. To reattach to the session later, use:
```bash
tmux attach -t playit
```

# Restart playit.gg client in Linux Mint
To restart the playit.gg client in Linux Mint, use the following command in your terminal:
```bash
sudo systemctl restart playit
```
You may check the status of the playit.gg client with:
```bash
systemctl status playit
```
You should see an output indicating that the playit.gg client is active and running like:
```bash
ricardo@OptiPlex-3070:~$ systemctl status playit
● playit.service - Playit Agent
     Loaded: loaded (/usr/lib/systemd/system/playit.service; enabled; preset: enabled)
     Active: active (running) since Tue 2026-01-20 16:51:03 CST; 8s ago
       Docs: https://playit.gg
   Main PID: 381628 (playit)
      Tasks: 10 (limit: 18859)
     Memory: 11.0M (peak: 46.1M swap: 116.0K swap peak: 17.0M)
        CPU: 18ms
     CGroup: /system.slice/playit.service
             ├─381628 /bin/bash /opt/playit/playit --secret_wait --secret_path /etc/playit/playit.toml -l /var/log/playit/playit.log start
             └─381630 /opt/playit/agent --secret_wait --secret_path /etc/playit/playit.toml -l /var/log/playit/playit.log start

ene 20 16:51:03 OptiPlex-3070 systemd[1]: Started playit.service - Playit Agent.
```


# Backup Hytale server files in Linux Mint

To backup Hytale server files in Linux Mint, you can use the following command in your terminal. This command will create backups of your server files at regular intervals.

```bash
java -Xms4G -Xmx4G -jar ~/Hytale/Server/HytaleServer.jar \
    --assets ~/Hytale/Assets.zip \
    --backup \
    --backup-dir ~/Hytale/Server/backups/public/RickyRaton \
    --backup-frequency 30 \
    --backup-max-count 48
```

# Run Hytale server with backups in Linux Mint as a background process
To run the Hytale server with backups in Linux Mint as a background process, use the following command in your terminal:

```bash
nohup java -Xms4G -Xmx4G -jar ~/Hytale/ServerRicky/HytaleServer.jar \
    --assets ~/Hytale/Assets.zip \
    --backup \
    --backup-dir ~/Hytale/Server/backups \
    --backup-frequency 30 \
    --backup-max-count 48 > hytale_server.log 2>&1 &
```

# To kill Hytale server running with backups in Linux Mint as a background process
Just like before,
To kill the Hytale server running with backups in Linux Mint as a background process, use the following command in your terminal:

```bash
pgrep -af HytaleServer.jar
```
This command will list the process ID (PID) of the Hytale server. You will see an output similar to this:
```bash
12345 java -Xms4G -Xmx4G -jar /home/ricardo/Hytale/Server/HytaleServer.jar --assets ...
```
Where `12345` is the PID of the Hytale server process.

# Run another world

```bash
nohup java -Xms4G -Xmx4G -jar ~/Hytale/Server/HytaleServer.jar \
    --assets ~/Hytale/Assets.zip \
    --backup \
    --backup-dir ~/Hytale/Server/backups/public/Teidar \
    --backup-frequency 30 \
    --backup-max-count 48 > hytale_server.log 2>&1 &
```

# Multiple worlds management in Linux Mint
To manage multiple worlds in Linux Mint, you can create separate directories for each world and run separate instances of the Hytale server for each world. Each instance can have its own configuration and backup settings.

For example, you can create directories for each Server:
```bash
mkdir -p ~/Hytale/ServerRicky
mkdir -p ~/Hytale/ServerTeidar
```
Then install the Hytale server files in each directory:
```bash
cp -r ~/Hytale/Server/* ~/Hytale/ServerRicky/
cp -r ~/Hytale/Server/* ~/Hytale/ServerTeidar/
```
Then, run separate instances of the Hytale server for each world:
```bash
cd ~/Hytale/ServerRicky
nohup java -jar ~/Hytale/ServerRicky/HytaleServer.jar \
--assets ~/Hytale/Assets.zip \
--bind 0.0.0.0:5520 \
> ~/hytale-Ricky-5520.log 2>&1 &
```
For the second world:
```bash
cd ~/Hytale/ServerTeidar
nohup java -jar ~/Hytale/ServerTeidar/HytaleServer.jar \
--assets ~/Hytale/Assets.zip \
--bind 0.0.0.0:5521 \
> ~/hytale-Teidar-5521.log 2>&1 &
```
Make sure to adjust the port numbers and paths as needed for your setup.
## Playit.gg urls for multiple worlds
- RickyRaton world: `washbowl-rep.gl.at.ply.gg:2330` redirected to `localhost:5520`
- Teidar world: `washbowl-pulling.gl.at.ply.gg:8334` redirected to `localhost:5521`