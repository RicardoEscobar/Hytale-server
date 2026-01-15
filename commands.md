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
