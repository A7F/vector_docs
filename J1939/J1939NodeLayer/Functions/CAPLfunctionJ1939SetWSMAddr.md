[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939SetWSMAddr.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939SetWSMAddr**

# J1939SetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939SetWSMAddr( dword ecuHandle, dword wsmAddress );
```

## Description

Use this function to set the address of the Working Set Master, if this ECU is a member of a working set. All parameter groups which are addressed to the Working Set Master are also received by an ECU which calls this function.

## Parameters

- **ecuHandle**: ECU handle
- **wsmAddress**: address of the Working Set Master for this ECU

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```plaintext
J1939SetWSMAddr( ecuHdl, 0x06 );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)