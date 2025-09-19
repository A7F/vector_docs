[J1939DestroyECU](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939DestroyECU.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939DestroyECU

# J1939DestroyECU

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939DestroyECU( dword ecuHandle );
```

## Description

This function deletes a logical node that was generated with [J1939CreateECU()](CAPLfunctionJ1939CreateECU.md) from the network.

**Important Note**

You should avoid allowing this function to be called within a CAPL callback function, since otherwise data consistency of the node layer could be violated.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```
J1939DestroyECU(ecuHandle);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
