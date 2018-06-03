# Claim your Linux Plex server from the shell

## Introduction

The Plex Media Server setup requires you to link your new server to your plex.tv account. This is done by initially accessing your server from "the same network" [1]. This can be a little "complicated" on a remote headless server if you have never heard of an "ssh tunnel" before.

The script in this git repo just uses the same mechanics that are used by the official Plex Docker image [2]. In fact, the script is just a refactored version of the Docker script.

## Usage

1. Make the script executable: `chmod +x plex-claim-server.sh`
2. Get your Plex Claim Code (it's only valid some minutes): https://www.plex.tv/claim/
3. Claim your server: `sudo -u plex ./plex-claim-server.sh "$YOUR_CLAIM_CODE"`
4. Restart your Plex Media Server, e.g. with `sudo systemctl restart plexmediaserver`

## Advanced Usage

Set the environment variable `PLEX_MEDIA_SERVER_APPLICATION_SUPPORT_DIR` to tell the script about your non-default Plex setup.

[1] https://support.plex.tv/articles/200288586-installation/#toc-2

[2] https://github.com/plexinc/pms-docker

