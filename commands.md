# To update Hytale server in Linux mint
`~/Hytale/hytale-downloader-linux-amd64` is the path to the Hytale downloader executable.
```bash
~/Hytale/hytale-downloader-linux-amd64
```

## Example command to update Hytale server in Linux Mint
```bash
ricardo@OptiPlex-3070:~$ ~/Hytale/hytale-downloader-linux-amd64
downloading latest ("release" patchline) to "2026.01.15-c04fdfe10.zip"
[==================================================] 100.0% (1.4 GB / 1.4 GB)B)
validating checksum...
successfully downloaded "release" patchline (version 2026.01.15-c04fdfe10)
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
nohup java -Xms4G -Xmx4G -jar ~/Hytale/Server/HytaleServer.jar \
    --assets ~/Hytale/Assets.zip \
    --backup \
    --backup-dir ~/Hytale/Server/backups/public/RickyRaton \
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
java -Xms4G -Xmx4G -jar ~/Hytale/Server/HytaleServer.jar \
    --assets ~/Hytale/Assets.zip \
    --backup \
    --backup-dir ~/Hytale/Server/backups/public/MasterViper \
    --backup-frequency 30 \
    --backup-max-count 48
```

