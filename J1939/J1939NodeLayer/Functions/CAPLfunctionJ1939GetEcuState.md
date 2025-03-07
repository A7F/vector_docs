[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939GetEcuState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetEcuState

# J1939GetEcuState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939GetEcuState(dword ecuHandle);
dword J1939GetEcuState(dbNode dbNode);
```

## Description

Returns the current state of the ECU.

## Parameters

- **ecuHandle**: ECU handle
- **dbNode**: node from database

## Return Values

- **0**: initialized
- **1**: claiming
- **2**: online
- **3**: offline

## Example

```plaintext
if (J1939GetEcuState( handle ) == 2) {
  write( "ECU is online" );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)