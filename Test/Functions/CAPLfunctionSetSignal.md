[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionSetSignal.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) / [Signal Access](../../SignalAccess/CAPLfunctionsSignalAccessOverview.md) » **SetSignal**

# SetSignal

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function replaces `SetSignalByTxNode`.

## Function Syntax

```plaintext
void setSignal(Signal aSignal, double aValue); // form 1
```

## Description

Sets the transmitted signal **aSignal** to the accompanying value.

If no suitable signal driver exists and thus no signal can be stimulated,

- in test modules/test units the verdict is set to "fail",
- in network nodes an error message is displayed in the Write Window.

**Note**

- It is recommended to use this form. The runtime environment is faster, because the signal object is determined during CAPL code compilation before measurement start.
- If you use the syntax of the special use case below, the signal object is determined during runtime which influences the performance.
- [Direct Access to Signals](../../../Shared/CAPL/SignalOrientedProgramming/SOPSetSignalValue.md)

## Parameters

- **aSignal**: Signal to be set.
- **aValue**: Physical value to be accepted.

## Return Values

—

## Example

**Example 1 — Signal is unique**

```plaintext
setSignal(OnOff, 1.0);
```

**Example 2 — Signal is ambiguous**

You have to use at minimum one more object to identify the signal uniquely. It could be any object from the list of possible objects, see [hints for resolving signal ambiguities](../../../Shared/CAPL/SignalOrientedProgramming/SOPSignalQualifying.md).

```plaintext
//Node and signal
setSignal(LightSwitch::OnOff, 1.0)
//Channel and signal
setSignal(CAN1::Status, 1)
```

## Special Use Case: Signal is not known before Measurement Start

### Function Syntax

```plaintext
long setSignal(char signalName[], double aValue); // form 2
```

### Description

Sets the transmitted signal **aSignal** to the accompanying value.

If no suitable signal driver exists and thus no signal can be stimulated, then in the test module the verdict of the test module is set to "fail". In the modeling library the measurement is stopped and an error message is displayed.

**Note**

- It is recommended to use this form only in special cases, because the signal object is determined during runtime which influences the performance.
- Reasons to use this string notation of the function:
  - Signal object is not known before measurement start.
  - In case of signal ambiguities the unique signal is determined during measurement.

### Parameters

- **signalName**: Name of the signal.

  **Note Signal Ambiguity**

  You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name.

  The exact qualification syntax is:  
  `[Channel::][Database name (alias)::][Node::][Message::]Signal`

  The order and completeness of the objects from right to left is important (see example).

- **aValue**: Physical value to be accepted.

### Return Values

- **0**: Signal exists
- **1**: Signal with given name does not exist

### Example

**Example 1 — Signal is unique**

```plaintext
setSignal("OnOff", 1.0);
```

**Example 2 — Signal is ambiguous**

```plaintext
//Message and signal
setSignal("LightState::OnOff", 1.0);
//Node, message and signal
setSignal("LightSwitch::LightState::OnOff", 1.0);
//Database name (alias), node, message and signal
setSignal("PowerTrain::LightSwitch::LightState::OnOff", 1.0);
setSignal("C11_Fy_Cluster::ESP::PDU_ESP_35::BTS_Bmg", 1);
//Channel, database name (alias), node, message and signal
setSignal("CAN1::PowerTrain::LightSwitch::LightState::OnOff", 1.0);
```

[SetRawSignal](CAPLfunctionSetRawSignal.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
