[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetMaxCurrentMode.md)

**CAPL Functions** » **VT System** » **SetMaxCurrentMode**

# SetMaxCurrentMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**: The function can only be called on system variable namespaces of channels that represent an external power supply in a power module VT7001.

## Method Syntax

- `long SysVarNamespace.SetMaxCurrentMode (dword Mode, double Factor); // form 1`
- `long SysVarNamespace.SetMaxCurrentMode (dword Mode); // form 2`

## Description

Sets the mode for the control voltage output to control the power supply's maximal output current.

## Parameters

- **Mode**
  - **0**: Max current control voltage output not active
  - **1**: Constant value, determined by the corresponding output system variable

- **Factor**
  - Factor to determine the control voltage from the defined (using the system variable or the wave form) power supply max current value.
  - `Power Supply Max Current * Factor = Control Voltage`
  - The factor has a default value of 1.0 at the start of measurement. If the function is called without factor parameter the currently set factor is kept.

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

In the following example the maximum current mode is activated on the power supply channel **ExtSupply** of a **VT7001** module. The max. current output is set to 10 A. Finally the output **Clamp30** of the **VT7001** is activated. To set a max current of 10 A, e.g. a control voltage of 5.0 V has to be given to the power supply. Therefore a factor of 0.5 has to be used.

### CAPL

```capl
SetMaxCurrentMode ()
{
  // Set mode to one power supply only -> external power supply 1
  sysvar::VTS::PowerSupply.SetInterconnectionMode(1);
  // Activate the maximum current mode with constant value mode
  // and a factor of 0.5
  sysvar::VTS::ExtSupply.SetMaxCurrentMode(1, 0.5);
  // Set power supply to max 10A
  @sysvar::VTS::ExtSupply::MaxCurrent = 10.0;
  // Switch output on
  @sysvar::VTS::Clamp30::Active = 1;
}
```

### .NET (C#)

```csharp
public void SetMaxCurrentMode()
{
    // Get VTS interface, VT7001 module, internal supply and a output channel
    IVTSystem vts = VTSystem.Instance;
    IVT7001 powerSupply = vts.GetModule("PowerSupply") as IVT7001;
    IVT7001SupplyExternal extSupply = vts.GetChannel("ExtSupply") as IVT7001SupplyExternal;
    IVT7001Channel clamp30 = vts.GetChannel("Clamp30") as IVT7001Channel;

    // Set mode to one power supply only -> external power supply 1
    powerSupply.InterconnectionMode.Value = InterconnectionMode.Sup1;

    // Activate the maximum current mode with constant value mode
    // and a factor of 0.5
    extSupply.SetMaxCurrentMode(MaxCurrentMode.Constant, 0.5);

    // Set power supply to max 10A
    extSupply.MaxCurrent.Value = 10.0;

    // Switch output on
    clamp30.Active.Value = OutputMode.Active;
}
```

### VT System Control

- Select **PowerSupply**
- Set **Sidebar** | **Interconnection Settings** | **Mode** to **sup1**
- Select **ExtSupply**
- Set **Sidebar** | **Output** | **Max Current Mode** to **Constant**
- Set **Sidebar** | **Output** | **Max Current Factor** to **0.5**
- Set **Sidebar** | **Output** | **Max Current** to **10.0**
- Select **Clamp30**
- Set **Schematic** | **Active** to **active**

[vtsSetMaxCurrentMode](CAPLfunctionVTSvtsSetMaxCurrentMode.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
