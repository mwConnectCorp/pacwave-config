# PacWave Config

Private configuration repository for PacWave sensor production tools.

## Contents

- **firmware-table.json** — Expected firmware versions for each sensor ID. Used by the PacWave Sensor app's production test tool to verify correct firmware is loaded on sensors during QC.

## Usage

The PacWave Sensor app fetches this file from the GitHub raw URL on launch (with local cache fallback). To update expected firmware versions, edit `firmware-table.json` and push — no app rebuild required.

### Raw URL

```
https://raw.githubusercontent.com/mwConnectCorp/pacwave-config/main/firmware-table.json
```

> **Note:** This is a private repo. The app uses a personal access token with `repo` scope to fetch this file.

## Schema

```json
{
  "version": <integer>,
  "lastUpdated": "<YYYY-MM-DD>",
  "sensors": [
    {
      "sensorId": <integer>,
      "name": "<string>",
      "expectedFirmwareVersion": <integer>
    }
  ]
}
```

Increment `version` when making changes so the app can detect updates.
