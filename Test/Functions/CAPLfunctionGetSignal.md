# getSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function replaces `getSignalByTxNode`.

## Function Syntax

```c
float getSignal(Signal aSignal); // form 1
```

## Description

Gets the value of a signal.

**Note**

- It is recommended to use this form. The runtime environment is faster, because the signal object is determined during CAPL code compilation before measurement start.
- If you use the syntax of the special use case below the signal object is determined during runtime which influences the performance.
- [Direct Access to Signals](../../../Shared/CAPL/SignalOrientedProgramming/SOPReadSignalValue.md)

## Parameters

- **aSignal**: The signal to be polled.

## Return Values

- If the signal is available (already appeared on the bus), this function returns the current signal value.
- If the signal is not yet available (did not appear on the bus until function call), this function returns the Initial Value of the database (GenSigStartValue).
- If a start value is defined in the **Start Values** window, or if the old signal value from the last measurement was taken over (options: Values of signal = **do not change**), this value is reported.

## Example

**Example 1 — Signal is unique**

```c
float value;
value = getSignal(OnOff);
```

**Example 2 — Signal is ambiguous**

```c
float value;
//Node and signal
value = getSignal(LightSwitch::OnOff);
//Channel and signal
value = getSignal(CAN1::Status);
```

## Special Use Case: Signal is not known before Measurement Start

### Function Syntax

```c
float getSignal(char signalName[]); // form 2
```

### Description

Gets the value of a signal.

**Note**

- It is recommended to use this form only in special cases, because the signal object is determined during runtime which influences the performance. Reasons to use this string notation of the function:
  - Signal object is not known before measurement start.
  - In case of signal ambiguities the unique signal is determined during measurement.
  - Special behavior for signals on **Ethernet PDUs** and **Autosar PDUs**. For performance reasons the signal value is only extracted and stored on demand. In most cases the signal is automatically registered for extraction and storing. For example when the signal is used in a panel, the signal is automatically registered. When the `getSignal(char signalName[])` function is used, automatic registration is not possible. Registration will occur the first time `getSignal(char signalName[])` is called. Please make sure `getSignal(char signalName[])` is called at least once before signal value updates occur, e.g. in the **on start** procedure.

### Parameters

- **signalName**: Name of the signal.

  **Note Signal Ambiguity**

  You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name.

  The exact qualification syntax is:  
  `[Channel::][Database name (alias)::][Node::][Message::]Signal`

  The order and completeness of the objects from right to left is important (see example).

### Return Values

- Value of the signal; 0.0 if the signal is not found.

### Example

**Example 1 — Signal is unique**

```c
float value;
value = getSignal("OnOff");
```

**Example 2 — Signal is ambiguous**

```c
float value;
//Message and signal
value = getSignal("LightState::OnOff");
//Node, message and signal
value = getSignal("LightSwitch::LightState::OnOff");
//Database name (alias), node, message and signal
value = getSignal("PowerTrain::LightSwitch::LightState::OnOff");
value = getSignal("C11_Fy_Cluster::ESP::PDU_ESP_35::BTS_Bmg");
//Channel, database name (alias), node, message and signal
value = getSignal("CAN1::PowerTrain::LightSwitch::LightState::OnOff");
```
