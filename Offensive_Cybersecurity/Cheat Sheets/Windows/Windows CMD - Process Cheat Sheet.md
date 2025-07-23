#Windows

# WIFI HACKING
## Verifier les reseau connus
```powershell
netsh wlan show profile
```

## Voir le reseau avec mot de passe en clair
```powershell
netsh wlan show profile name="..." key=clear
```

## Voir les reseau disponible
```powershell
netsh wlan show networks mode=bssid
```

# PC HEALTH STATUS

## Basic Health check
```powershell
dism /online /cleanup-image /checkhealth
``` 
- Run as an administrative command prompt or in an administrative PowerShell session

#### If above command finds anything to report, run to clean things up
```powershell
dism /online /cleanup-image /restorehealth 
```

## Other health scan 
```powershell
sfc /scannow
```

## Check performance reliability 
``` powershell
perfmon /rel
```

### CHECK GRAPHIC DRIVERS###