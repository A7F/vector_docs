# vtsSetInterconnectionMode

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetInterconnectionMode

### Valid for: CANoe DE • CANoe:lite DE

**Note**  
This function may not be called in any CAPL handler routines or in ECU nodes. It may only be called in the context of the MainTest method of a test module. Use a test module that automatically runs at the start of measurement to set an initial state.

## Function Syntax

```plaintext
long vtsSetInterconnectionMode (char Target[], eVTSInterconnectionMode Mode);
```

## Description

Sets the mode for interconnection of the three possible power supplies and the two power outputs of the power module VT7001.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Mode**: Values see [eVTSInterconnectionMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSInterconnectionMode)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. It is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

**CAPL**

```plaintext
InternalPowerSupply ()
{
  // Set mode to one power supply only -> internal power supply
  vtsSetInterconnectionMode("VTS::PowerSupply", eVTSInterconnectionModeSupInt);

  // Set voltage to 12.0 V
  vtsSetRefVoltageMode("VTS::IntSupply", 1);
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

**.NET (C#)**

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

**VT System Control**

- Select **PowerSupply**
- Set **Sidebar** | **Interconnection Settings** | **Mode** to **supint**
- Select **IntSupply**
- Set **Sidebar** | **Output** | **Ref Voltage Mode** to **Constant**
- Set **Sidebar** | **Output** | **Ref Voltage** to **12.0**
- Select **Clamp30**
- Set **Schematic** | **Active** to **active**
- Select **Clamp15**
- Set **Schematic** | **Active** to **active**
- Check measurement values 'AvgCurrent'

[SetInterconnectionMode](CAPLfunctionVTSSetInterconnectionMode.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)