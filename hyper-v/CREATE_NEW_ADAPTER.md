# Create New V-Switch
Creating virtual switches for Hyper-V using PowerShell involves using the `New-VMSwitch` cmdlet. Here's a basic example of how you can create a virtual switch using PowerShell:

```powershell
# Define the function
function New-VAdapter {
    # Prompt user for switch name
    $switchName = Read-Host "Enter the virtual switch name"

    # Prompt user for switch type
    $switchType = Read-Host "Enter the virtual switch type (External/Internal/Private)"

    # Prompt user for network adapter name
    $networkAdapterName = Read-Host "Enter the physical network adapter name"

    # Create the virtual switch
    New-VMSwitch -Name $switchName -SwitchType $switchType -NetAdapterName $networkAdapterName
}

# Set an alias for the function
Set-Alias -Name "New-VAdapter" -Value New-VAdapter

```

Explanation of parameters:
- `$switchName`: Specify a name for your virtual switch.
- `$switchType`: Choose the type of switch, which can be "External," "Internal," or "Private."
- `$networkAdapterName`: Provide the name of the physical network adapter to which the virtual switch will be connected. You can get the available network adapters using the `Get-NetAdapter` cmdlet.

Make sure to run this script with elevated privileges, as creating virtual switches requires administrative rights.

Adjust the values of `$switchName`, `$switchType`, and `$networkAdapterName` according to your specific requirements.

> *Note*: If you are creating an external switch, ensure that the physical network adapter is not already bound to another protocol or service.
