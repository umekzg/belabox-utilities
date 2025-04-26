# BELABOX Cloud Remote Development Patch

This patch changes the remote endpoint in belaUI from `remote.belabox.net` to `10.5.0.120` for development purposes.

## Purpose

The BELABOX encoder connects via WebSocket to the BELABOX cloud remote server for remote management. This patch allows you to use a development server at `10.5.0.120` instead of the production server.

## How to Apply the Patch

1. Navigate to your belaUI installation directory:
   ```
   cd /path/to/belaUI
   ```

2. Apply the patch:
   ```
   patch -p1 < /path/to/belabox-cloud-remote.patch
   ```

3. Restart the belaUI service:
   ```
   sudo systemctl restart belaui
   ```

## Changes Made by the Patch

The patch makes the following changes:

1. Changes the `remoteEndpointHost` from `remote.belabox.net` to `10.5.0.120`
2. Updates the `remoteProtocolVersion` from 14 to 15 to distinguish development connections
3. Adds a comment at the top of the file explaining the purpose of the patch

## Reverting the Patch

To revert the patch and restore the original settings:

1. Navigate to your belaUI installation directory:
   ```
   cd /path/to/belaUI
   ```

2. Revert the patch:
   ```
   patch -p1 -R < /path/to/belabox-cloud-remote.patch
   ```

3. Restart the belaUI service:
   ```
   sudo systemctl restart belaui
   ```

## License

This patch is provided under the same license as the original belaUI project (GPL-3.0).
