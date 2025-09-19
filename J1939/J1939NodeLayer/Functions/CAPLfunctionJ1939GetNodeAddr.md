[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939GetNodeAddr.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetNodeAddr

# J1939GetNodeAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939GetNodeAddr( dword ecuHandle );
```

## Description

This function returns the current address of a logical ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- current ECU address
- 0xFE if the address is the J1939 NULL address. If this function is called with an invalid handle, the function returns 0xFFFF.

## Example

```plaintext
addr = J1939GetNodeAddr(ecuHandle);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
