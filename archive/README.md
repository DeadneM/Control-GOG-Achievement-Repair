# Archived source snapshot

The V0.9 source is stored as gzip + base64 text so the exact tested snapshot can be preserved losslessly.

## Windows PowerShell

```powershell
$b64 = Get-Content -Raw .\Control_GOG_Achievement_Repair_V9_NATIVE_FIRST.go.gz.b64
[IO.File]::WriteAllBytes("source.go.gz", [Convert]::FromBase64String($b64))
gzip -d .\source.go.gz
Rename-Item .\source.go Control_GOG_Achievement_Repair_V9_NATIVE_FIRST.go
```

## Linux / macOS

```bash
base64 -d Control_GOG_Achievement_Repair_V9_NATIVE_FIRST.go.gz.b64 > source.go.gz
gzip -d source.go.gz
mv source.go Control_GOG_Achievement_Repair_V9_NATIVE_FIRST.go
```

Expected SHA-256 of the reconstructed Go source:

`dfa768927b98ba68b87c1865dfd1b75d6b9c249f5389e7f9e3087ca8271a1bbc`
