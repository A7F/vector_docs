[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetRefVoltageMode.md)

## CAPL Functions » VT System » vtsSetRefVoltageMode

### vtsSetRefVoltageMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

### Function Syntax

- `long vtsSetRefVoltageMode (char Target[], eVTSRefVoltageMode Mode); // form 1`
- `long vtsSetRefVoltageMode (char Target[], eVTSRefVoltageMode Mode, double Factor); // form 2`

### Description

Sets the mode for the reference voltage output to control the power supply's output voltage.

### Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Mode**: Values see [eVTSRefVoltageMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSRefVoltageMode)
- **Factor**: Factor (Ref voltage factor) to determine the control voltage from the defined power supply output voltage.

  **Notice!** The factor is given by the external power supply. This factor is the ratio of the control voltage to the output voltage. For example, if a power supply outputs 50 V at a control voltage of 5 V, its factor is 0.1 (5/50).

  Use form 1 for the internal power supply - the factor is always 1.

  Use form 2 with explicitly given factor for the external power supplies. The default factor is 1.0.

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

### Example

In order to output a control voltage (V`<sub>`Control`</sub>`) which leads to the desired output voltage V`<sub>`Out`</sub>`, the VT7001 must know the power supply factor.

In the following example, the factor of the external power supply is 0.1 and the desired output voltage V`<sub>`Out`</sub>` is 15 V.

To achieve the desired output voltage (V`<sub>`Out`</sub>`), the VT7001 calculates and sets the control voltage (V`<sub>`Control`</sub>`) automatically (1.5 V =15 * 0.1), which results in an output voltage of 15 V.

#### CAPL

```capl
SetRefVoltageMode ()
{
  // Set mode to one power supply only -> external power supply 1
  vtsSetInterconnectionMode("VTS::PowerSupply", eVTSInterconnectionModeSup1);

  // The factor 0.1 of the external power supply is transmitted to the VT7001
  vtsSetRefVoltageMode("VTS::ExtSupply", eVTSRefVoltageModeConstant, 0.1);

  // The following line sets the output voltage to 15 V,
  // VControl (1.5 V) is calculated with the given factor automatically
  @sysvar::VTS::ExtSupply::RefVoltage = 15;

  // Switch output on
  @sysvar::VTS::Clamp30::Active = eVTSOutputModeActive;
}
```

#### .NET (C#)

```csharp
public void SetRefVoltageMode()
{
  // Get VTS interface, VT7001 module, internal supply and a output channel
  IVTSystem vts = VTSystem.Instance;
  IVT7001 powerSupply = vts.GetModule("PowerSupply") as IVT7001;
  IVT7001SupplyExternal extSupply = vts.GetChannel("ExtSupply") as IVT7001SupplyExternal;
  IVT7001Channel clamp30 = vts.GetChannel("Clamp30") as IVT7001Channel;

  // Set mode to one power supply only -> external power supply 1
  powerSupply.InterconnectionMode.Value = InterconnectionMode.Sup1;

  // Activate the reference voltage mode with constant value mode
  // and a factor of 0.1
  extSupply.SetRefVoltageMode(RefVoltageMode.Constant, 0.1);

  // The following line sets the output voltage to 15 V,
  // VControl (1.5 V) is calculated with the given factor automatically
  extSupply.RefVoltage.Value = 15.0;

  // Switch output on
  clamp30.Active.Value = OutputMode.Active;
}
```

#### VT System Control

[VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

Select **PowerSupply**

Set **Sidebar** | **Interconnection Settings** | **Mode** to **sup1**

Select **ExtSupply**

Set **Sidebar** | **Output** | **Ref Voltage Mode** to **Constant**  
Set **Sidebar** | **Output** | **Ref Voltage Factor** to **0.1**  
Set **Sidebar** | **Output** | **RefVoltage** to **15.0**

Select **Clamp30**

Set **Schematic** | **Active** to **active**

[SetRefVoltageMode](CAPLfunctionVTSSetRefVoltageMode.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
