[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionGetSignalTime.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) / [Signal Access](../../SignalAccess/CAPLfunctionsSignalAccessOverview.md) » getSignalTime

# getSignalTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function replaces `getSignalTimeByTxNode`.

## Function Syntax

```
dword getSignalTime(Signal aSignal); // form 1
```

## Description

Gets the time point (unit: 10 microseconds) relative to the measurement start at which the signal was last sent on the bus.

**Note**  
It is recommended to use form 1. The runtime environment is faster with form 1, because the signal object is determined during CAPL code compilation before measurement start. With **form 2** the signal object is determined during runtime which influences the performance.

## Parameters

- **aSignal**: The signal to be polled.

## Return Values

Time point or 0 if the signal was not sent yet.

## Example

```c
dword timePoint;
timePoint = getSignalTime(Node_SUT::CrashDetected);
```

## Special Use Case: Signal is not known before Measurement Start

### Function Syntax

```
dword getSignalTime(char signalName[]); // form 2
```

### Description

Gets the time point (unit: 10 microseconds) relative to the measurement start at which the signal was last sent on the bus.

**Note**  
It is recommended to use this form only in special cases, because the signal object is determined during runtime which influences the performance.

Reasons to use this string notation of the function:

- Signal object is not known before measurement start.
- In case of signal ambiguities the unique signal is determined during measurement.

### Parameters

- **signalName**: Name of the signal.

**Note Signal Ambiguity**  
You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name.

The exact qualification syntax is:  
`[Channel::][Database name (alias)::][Node::][Message::]Signal`

The order and completeness of the objects from right to left is important (see example).

### Return Values

Time point or 0 if the signal was not sent yet.

### Example

**Example 1 — Signal is unique**

```c
dword timePoint;
timePoint = getSignalTime("CrashDetected");
```

**Example 2 — Signal is ambiguous**

```c
float value;
// Message and signal
value = getSignal("LightState::OnOff");
// Node, message and signal
value = getSignal("LightSwitch::LightState::OnOff");
// Database name (alias), node, message and signal
value = getSignal("PowerTrain::LightSwitch::LightState::OnOff");
value = getSignal("C11_Fy_Cluster::ESP::PDU_ESP_35::BTS_Bmg");
// Channel, database name (alias), node, message and signal
value = getSignal("CAN1::PowerTrain::LightSwitch::LightState::OnOff");
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)