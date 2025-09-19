[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionGetRawSignal.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) / [Signal Access](../../SignalAccess/CAPLfunctionsSignalAccessOverview.md) » GetRawSignal

# GetRawSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `Int64 GetRawSignal(dbSignal aSignal);` // form 1
- `long GetRawSignal(dbSignal aSignal, byte data[], dword dataLength);` // form 2

## Description

Retrieves the current raw value of a signal. These functions can be used for signals with more than 32 bits length. If the signal name is statically known, you can also use **$`<signal>`.raw64** since 7.5 Service Pack 2.

## Parameters

- **dbSignal**: The signal.
- **data**: Receives the data bytes of the signal.
- **dataLength**: Length of the data buffer.

## Return Values

- **Form 1**: the current raw value of the signal
- **Form 2**:
  - Number of bytes written to the data buffer (minimum of **dataLength** and the size of the signal's data type)
  - -1 on error

## Example

—

## Special Use Case: Signal is not known before Measurement Start

### Function Syntax

- `Int64 GetRawSignal(char name[]);` // form 3
- `long GetRawSignal(char name[], byte data[], dword dataLength);` // form 4

### Description

Retrieves the current raw value of a signal. These functions can be used for signals with more than 32 bits length. If the signal name is statically known, you can also use **$`<signal>`.raw64** since 7.5 Service Pack 2.

### Parameters

- **name**: Name of the signal.
  - **Signal Ambiguity**: You have to use further objects to identify the signal uniquely. They are: channel, database name (alias), node name and message name.
  - The exact qualification syntax is: `[Channel::][Database name (alias)::][Node::][Message::]Signal`
- **dbSignal**: The signal.
- **data**: Receives the data bytes of the signal.
- **dataLength**: Length of the data buffer.

### Return Values

- **Form 3**:
  - Current raw value of the signal
  - -2: Signal is not found
- **Form 4**:
  - Number of bytes written to the data buffer (minimum of **dataLength** and the size of the signal's data type)
  - -2: Signal is not found
  - -1: Other errors

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
