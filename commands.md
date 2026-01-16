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
