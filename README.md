# PC to GoldHEN PS4 PKG Loader

Transfer PKG files from a Linux PC to a PS4 over your local network using GoldHEN FTP. No USB drive required.

## 1. Enable FTP on the PS4

On the PS4, go to:

**GoldHEN → Server Settings → Enable FTP Server**

## 2. Connect from Linux

Install `lftp`:

```bash
sudo apt install lftp
```

Connect using your PS4's IP address:

```bash
lftp -u anonymous, ftp://<PS4-IP>:2121
```

Replace `<PS4-IP>` with your PS4's actual IP address.

## 3. Create the PKG folder and upload

At the `lftp` prompt, create the folder:

```text
mkdir /data/pkg
```

Upload your PKG directly into it:

```text
put <path-to-your-pkg-file> -o /data/pkg/<package-name>.pkg
```

Check the uploaded file:

```text
ls /data/pkg
```

## 4. Set the Package Source

On the PS4, go to:

**GoldHEN Settings → Debug Settings → Package Source**

- Change the default source from `USB` to `HDD`.
- Check the displayed package path. It is most likely `hdd:/data/pkg/`.

## 5. Install the PKG

Open the PS4 Package Installer and select the uploaded package :>
