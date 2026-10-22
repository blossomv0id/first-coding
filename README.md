# Define the Lightspeed Filter Agent Extension ID and update URL
$ExtensionId = "edeehpcbfibhgpnnipaepekmdpfdeocl"
$UpdateUrl = "https://microsoft.com"
$RegistryPath = "HKLM:\SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist"

# Create registry path if it doesn't exist
if (-not (Test-Path $RegistryPath)) {
    New-Item -Path $RegistryPath -Force | Out-Null
}

# Add the extension to the force-install list
New-ItemProperty -Path $RegistryPath -Name "1" -Value "$ExtensionId;$UpdateUrl" -PropertyType String -Force
#!/bin/bash
# Force install Lightspeed Filter Agent on Google Chrome for macOS
TARGET_DIR="/Library/Preferences/com.google.Chrome.plist"

sudo defaults write com.google.Chrome ExtensionInstallForcelist -array-add "adcoljhdbeonafmggmhdipgconijiccl;https://google.com"
// Conceptual breakdown of the agent's video management loop
for (let i in elementsArray) {
    if (!elementsArray[i].paused) {
        console.debug('[LS Filter] pausing media asset');
        elementsArray[i].pause(); 
    }
}
