# The world is gone.

```bash
ricardo@OptiPlex-3070:~/Hytale/Server$ ~/Hytale/hytale-downloader-linux-amd64
Please visit the following URL to authenticate:
https://oauth.accounts.hytale.com/oauth2/device/verify?user_code=nYwDHXNq
Or visit the following URL and enter the code:
https://oauth.accounts.hytale.com/oauth2/device/verify
Authorization code: nYwDHXNq
downloading latest ("release" patchline) to "2026.01.17-4b0f30090.zip"
[==================================================] 100.0% (1.4 GB / 1.4 GB)B)
validating checksum...
successfully downloaded "release" patchline (version 2026.01.17-4b0f30090)
ricardo@OptiPlex-3070:~/Hytale/Server$ java -Xms4G -Xmx4G -jar ~/Hytale/Server/HytaleServer.jar \
    --assets ~/Hytale/Assets.zip \
    --backup \
    --backup-dir ./backups \
    --backup-frequency 30 \
    --backup-max-count 48
```

After doing that my world was gone. And it was replaced with a new empty world.
How do I fix this?
It looks like when you updated your Hytale server using the `hytale-downloader-linux-amd64` tool, it may have created a new world instead of preserving your existing one. Here are some steps you can take to try and recover your original world:

