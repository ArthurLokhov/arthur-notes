# Setting up my work environment(Linux)

## Install and configure .Net
1. Install Snap
```
sudo rm /etc/apt/prefernces.d/nosnap.pref
sudo apt-get update && sudo apt-get install snapd
sudo snap version
```
2. Install .Net
```
sudo snap install dotnet-sdk --classic --channel=[version]
sudo snap alias dotnet-sdk.dotnet dotnet
```
 
3. Export .Net Path
```
export DOTNET_ROOT=/snap/dotnet-sdk/current
```