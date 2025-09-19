[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetLength.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthGetLength

# AREthGetLength

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthGetLength ( dword messageHandle );
```

## Description

This function returns the length in bytes that is in the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnAREthMessage](CAPLfunctionOnAREthMessage.md))

## Return Values

- **Length of the SOME/IP message** (without Message ID and length field)
- In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

—

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
