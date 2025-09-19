# AfdxGetSignalInt64

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetSignalInt64.md)

**CAPL Functions** » **AFDX** » **AfdxGetSignalInt64**

## Function Syntax

- `long AfdxGetSignalInt64( long packet, char* signalName ); // form 1`
- `long AfdxGetSignalInt64( long packet, long offset ); // form 2`

## Description

This function returns the value of a 64-bit integer signal.

## Parameters

- **packet**: Handle of the message.
- **offset**: The offset value points to the starting byte of the 64-bit integer value in the AFDX payload area.
- **signalName**: Name of the signal.
  - **Note:** The signal and its message need to be defined in the assigned DBC file.

## Return Values

- **Signal value**: Call [AfdxGetLastErrror()](CAPLfunctionAfdxGetLastError.md) to check for errors in the call.

## Example

—

**See Also**

- [AfdxGetSignalInt64](#aanchor22551)
