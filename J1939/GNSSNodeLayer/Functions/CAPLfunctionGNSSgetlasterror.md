[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetlasterror.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSGetLastError

# GNSSGetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSGetLastError();
```

## Description

This function returns the error status of the last GNSS function of a node to be performed. The individual error states are described [here](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md).

## Parameters

—

## Return Values

[Error state](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md) of the last performed function

## Example

```plaintext
GNSSStartSimulation( 0 );
if (GNSSGetLastError() != 0) {
  write("Start of simulation failed");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
