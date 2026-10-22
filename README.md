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
