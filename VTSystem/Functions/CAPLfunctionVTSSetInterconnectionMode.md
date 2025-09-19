[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetInterconnectionMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SetInterconnectionMode

# SetInterconnectionMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**

The function can only be called on system variable namespaces of the VT System power module VT7001 (namespace that represents the whole module). This function may not be called in any CAPL handler routines or in ECU nodes. It may only be called in the context of the MainTest method of a test module. Use a test module that automatically runs at the start of measurement to set an initial state.

## Method Syntax

Long SysVarNamespace.SetInterconnectionMode (eVTSInterconnectionMode Mode);

## Description

Sets the mode for interconnection of the three possible power supplies and the two power outputs of the power module VT7001.

## Parameters

- **Mode**: Values see [eVTSInterconnectionMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSInterconnectionMode)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

The internal power supply unit delivers power and the ECU is connected to OUT1 (clamp 30), OUT2 (clamp 15) and GND1 (clamp 31). In this example, the channel for the internal power supply unit is named "IntSupply", the two output channels are named "Clamp30" and "Clamp15", and the VT7001 module is named "PowerSupply".

### CAPL

```capl
InternalPowerSupply ()
{
  // Set mode to one power supply only -> internal power supply
  sysvar::VTS::PowerSupply.SetInterconnectionMode(eVTSInterconnectionModeSupInt);

  // Set voltage to 12.0 V
  sysvar::VTS::IntSupply.SetRefVoltageMode(1);
  @sysvar::VTS::IntSupply::RefVoltage = 12.0;

  // Switch both outputs on
  @sysvar::VTS::Clamp30::Active = eVTSOutputModeActive;
  @sysvar::VTS::Clamp15::Active = eVTSOutputModeActive;

  // Measure the current consumed by the ECU via clamp 15
  // after 2 seconds (result is written to the Write Window)
  TestWaitForTimeOut(2000);
  write("ECU is consuming %fmA.", @sysvar::VTS::Clamp30::AvgCurrent);
}
```

### .NET (C#)

```csharp
public void InternalPowerSupply()
{
    // Get VTS interface, VT7001 module, internal supply and two output channels
    IVTSystem vts = VTSystem.Instance;
    IVT7001 powerSupply = vts.GetModule("PowerSupply") as IVT7001;
    IVT7001SupplyInternal intSupply = vts.GetChannel("IntSupply") as IVT7001SupplyInternal;
    IVT7001Channel clamp30 = vts.GetChannel("Clamp30") as IVT7001Channel;
    IVT7001Channel clamp15 = vts.GetChannel("Clamp15") as IVT7001Channel;

    // Set mode to one power supply only -> external power supply 1
    powerSupply.InterconnectionMode.Value = InterconnectionMode.SupInt;

    // Set voltage to 12.0 V
    intSupply.SetRefVoltageMode(RefVoltageMode.Constant);
    intSupply.RefVoltage.Value = 12.0;

    // Switch both outputs on
    clamp30.Active.Value = OutputMode.Active;
    clamp15.Active.Value = OutputMode.Active;

    // Measure the current consumed by the ECU via clamp 15
    // after 2 seconds (result is written to the Write Window)
    Vector.CANoe.Threading.Execution.Wait(2000);
    Vector.Tools.Output.WriteLine("ECU is consuming " + clamp30.AvgCurrent.Value + "mA");
}
```

### VT System Control

[VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

- Select **PowerSupply**
- Set **Sidebar** | **Interconnection Settings** | **Mode** to **supint**
- Select **IntSupply**
- Set **Sidebar** | **Output** | **Ref Voltage Mode** to **Constant**
- Set **Sidebar** | **Output** | **Ref Voltage** to **12.0**
- Select **Clamp30**
- Set **Schematic** | **Active** to **active**
- Select **Clamp15**
- Set **Schematic** | **Active** to **active**

[Check measurement values 'AvgCurrent']

[vtsSetInterconnectionMode](CAPLfunctionVTSvtsSetInterconnectionMode.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
