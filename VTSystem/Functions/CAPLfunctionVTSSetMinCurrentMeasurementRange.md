[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetMinCurrentMeasurementRange.md)

**CAPL Functions** » **VT System** » **SetMinCurrentMeasurementRange**

# SetMinCurrentMeasurementRange

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

## Method Syntax

- `long SysVarNamespace.SetMinCurrentMeasurementRange (dword range); // VT7001`
- `long SysVarNamespace.SetMinCurrentMeasurementRange (eVTS2808CurrentMeasurementRange range); // VT2808`

## Description

Sets the current measurement range that should be used by the automatic measuring range changeover of the **VT7001**/**VT2808** module. Amperage ranges below the ranges set in **range** parameter will no longer be used. This prevents a measuring range changeover in dedicated situations.

Even if the measuring range for a specified amperage is not used, this does not mean that no measurement is possible. Since the optimal Shunt is not used in such situations, the accuracy of the measurement decreases below the given value in the manual. The accuracy decreases all the more the more the used measuring range differs from the optimum. Therefore the range should be set advisedly.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Range**: Determines up to which range the automatic measuring range changeover may change over.
  - Ranges for **VT7001** module: Values see [eVTSCurrentMeasurementRange](../CAPLfunctionsVTSystemEnumeration.md#eVTSCurrentMeasurementRange)
  - Ranges for **VT2808** module: Values see [eVTS2808CurrentMeasurementRange](../CAPLfunctionsVTSystemEnumeration.md#eVTS2808CurrentMeasurementRange)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

**Example for VT7001**  
This example shows how the measuring ranges up to 100mA are locked for a measurement before a load will be switched on:

### CAPL

```plaintext
PerformMeasurementAtActivation()
{
  // Prepare VT7001 module (External power supply with fixed voltage is
  // connected to PS1 connector)
  sysvar::VTS::ECUSupplyModule.SetInterconnectionMode(eVTSInterconnectionModeSup1);

  // Configure output to use current measurement ranges for more than 100mA
  // and wait for setting to be applied. A current below 1A is expected at
  // activation so no measuring range changeover should take place.
  sysvar::VTS::ECUSupply.SetMinCurrentMeasurementRange(eVTSCurrentMeasurementRange1A);
  TestWaitForTimeOut(50);

  // activate supply output
  @sysvar::VTS::ECUSupply::Active = 1;

  // activation can be measured without measuring range changeover
}
```

### .NET (C#)

—

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

- Select **ECUSupplyModule**
- Set **Sidebar** | **Interconnection Settings** | **Mode** to **sup1**
- Select **ECUSupply**
- Set **Sidebar** | **General** | **Min Meas. Range** to **1A**
- Set **Schematic** | **Active** to **active**

[vtsSetMinCurrentMeasurementRange](CAPLfunctionVTSvtsSetMinCurrentMeasurementRange.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
