[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetLoadMode.md)

**CAPL Functions** » **VT System** » **SetLoadMode**

# SetLoadMode

**Valid for**: CANoe DE • CANoe:lite DE

**Note**: The function can only be called on system variable namespaces of channels belonging to the VT System module VT1004 or VT1104.

## Method Syntax

`long SysVarNamespace.SetLoadMode (eVTSLoadMode Mode);`

## Description

Switches the internal load to a specific mode.

## Parameters

- **Mode**: Values see [eVTSLoadMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSLoadMode)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT system. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

The following example demonstrates the usage of the internal load of a VT1004 channel. In this example the channel is called **LowBeamLeft**. The internal load is configured for resistance-control-mode with a resistance of 120 Ohm. So the electronic load functions as a constant resistor against the input.

The second part of the example shows how to use the current control mode. Here the electronic load is regulated so that a constant current flows between the two ECU lines.

### CAPL

```plaintext
InternalLoad_ResistanceControl ()
{
  // Set the resistor of the internal load to 120Ohm
  @sysvar::VTS::LowBeamLeft::IntLoadResistor = 120;

  // Set internal load mode to resistance control
  sysvar::VTS::LowBeamLeft.SetLoadMode(eVTSLoadModeResistanceControl);

  // Connect ECU with internal load
  @sysvar::VTS::LowBeamLeft::RelayIntLoadA = 1;
  @sysvar::VTS::LowBeamLeft::RelayIntLoadB = 1;
}

InternalLoad_CurrentControl ()
{
  // Set the current of the internal load to 1A
  @sysvar::VTS::LowBeamLeft::IntLoadCurrent = 1;

  // Set internal load mode to current control
  sysvar::VTS::LowBeamLeft.SetLoadMode(eVTSLoadModeResistanceControl);

  // Connect ECU with internal load
  @sysvar::VTS::LowBeamLeft::RelayIntLoadA = 1;
  @sysvar::VTS::LowBeamLeft::RelayIntLoadB = 1;
}
```

### .NET (C#)

```csharp
public void InternalLoad_ResistanceControl()
{
    // Get VTS interface and VT1004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT1004Channel lowBeamLeft = vts.GetChannel("LowBeamLeft") as IVT1004Channel;

    // Set the resistor of the internal load to 120Ohm
    lowBeamLeft.IntLoadResistor.Value = 120.0;

    // Set internal load mode to resistance control
    lowBeamLeft.LoadMode.Value = LoadMode.ResistanceControl;

    // Connect ECU with internal load
    lowBeamLeft.RelayIntLoadA.Value = true;
    lowBeamLeft.RelayIntLoadB.Value = true;
}

public void InternalLoad_CurrentControl()
{
    // Get VTS interface and VT1004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT1004Channel lowBeamLeft = vts.GetChannel("LowBeamLeft") as IVT1004Channel;

    // Set the current of the internal load to 1A
    lowBeamLeft.IntLoadCurrent.Value = 1.0;

    // Set internal load mode to current control
    lowBeamLeft.LoadMode.Value = LoadMode.CurrentControl;

    // Connect ECU with internal load
    lowBeamLeft.RelayIntLoadA.Value = true;
    lowBeamLeft.RelayIntLoadB.Value = true;
}
```

### VT System Control

Select **LowBeamLeft**

- Configure resistance mode
  - Set **Sidebar** | **Internal Load** | **Set Resistance** to **120.0**
  - Set **Sidebar** | **Internal Load** | **Load Mode** to **Resistance**
  - Set **Schematic** | **RelayIntLoadA, RelayIntLoadB** to **closed**
- Configure current mode
  - Set **Sidebar** | **Internal Load** | **Set Current** to **1.0**
  - Set **Sidebar** | **Internal Load** | **Load Mode** to **Current**
  - Set **Schematic** | **RelayIntLoadA, RelayIntLoadB** to **closed**

[vtsSetLoadMode](CAPLfunctionVTSvtsSetLoadMode.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
