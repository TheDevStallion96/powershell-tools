Creating virtual switches for Hyper-V using PowerShell involves using the `New-VMSwitch` cmdlet. Here's a basic example of how you can create a virtual switch using PowerShell:

```powershell
# Define the parameters
$switchName = "MyVirtualSwitch"
$switchType = "External"  # You can use "Internal" or "Private" as well
$networkAdapterName = "PhysicalNetworkAdapterName"

# Create the virtual switch
New-VMSwitch -Name $switchName -SwitchType $switchType -NetAdapterName $networkAdapterName
```

Explanation of parameters:
- `$switchName`: Specify a name for your virtual switch.
- `$switchType`: Choose the type of switch, which can be "External," "Internal," or "Private."
- `$networkAdapterName`: Provide the name of the physical network adapter to which the virtual switch will be connected. You can get the available network adapters using the `Get-NetAdapter` cmdlet.

Make sure to run this script with elevated privileges, as creating virtual switches requires administrative rights.

Adjust the values of `$switchName`, `$switchType`, and `$networkAdapterName` according to your specific requirements.

Note: If you are creating an external switch, ensure that the physical network adapter is not already bound to another protocol or service.
