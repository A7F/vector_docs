[J1939GetWSMAddr](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939GetWSMAddr.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetWSMAddr

# J1939GetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetWSMAddr( dword ecuHandle );
```

## Description

This function returns the address of the Working Set Master, which is assigned to this ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

Address of the Working Set Master for this ECU or the Null-Address (0xFE)

## Example

```plaintext
addr = J1939GetWSMAddr( ecuHdl );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
