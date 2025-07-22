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

##
dism /online /cleanup-image /checkhealth 
#(run at an administrative command prompt or in an administrative PowerShell session)

#if this command finds anything to report, run 
dism /online /cleanup-image /restorehealth 
#to clean things up

## Other scan 
sfc /scannow

## Check performance reliability 
``` powershell
perfmon /rel
```

### CHECK GRAPHIC DRIVERS###