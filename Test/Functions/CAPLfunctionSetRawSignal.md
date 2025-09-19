[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionSetRawSignal.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) / [Signal Access](../../SignalAccess/CAPLfunctionsSignalAccessOverview.md) » SetRawSignal

# SetRawSignal

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SetRawSignal(dbSignal aSignal, int64 value); // form 1
void SetRawSignal(dbSignal aSignal, byte data[], dword dataLength); // form 2
```

## Description

Sets the raw value of a signal. These functions can be used for signals with more than 32 bits length. If the signal name is statically known, you can also use **$`<signal>`.raw64** since 7.5 Service Pack 2.

## Parameters

- **dbSignal**: The signal.
- **value**: Signal value to be set.
- **data**: The data bytes of the signal.
- **dataLength**: Length of the data.

## Return Values

Form 2

- **0**: on success
- **-1**: on error

## Example

—

## Special Use Case: Signal is not known before Measurement Start

### Function Syntax

```plaintext
void SetRawSignal(char name[], int64 value); // form 3
long SetRawSignal(char name[], byte data[], dword dataLength); // form 4
```

### Description

Sets the raw value of a signal. These functions can be used for signals with more than 32 bits length. If the signal name is statically known, you can also use **$`<signal>`.raw64** since 7.5 Service Pack 2.

### Parameters

- **name**: Name of the signal.
  - **Signal Ambiguity**: You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name.
  - **Qualification Syntax**: `[Channel::][Database name (alias)::][Node::][Message::]Signal`
- **value**: Signal value to be set.
- **data**: The data bytes of the signal.
- **dataLength**: Length of the data.

### Return Values

Form 4

- **0**: on success
- **-2**: if signal not found
- **-1**: on other error

### Example

—

[SetSignal](CAPLfunctionSetSignal.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
