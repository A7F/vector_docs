[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429StopTx.md)

[CAPL Functions](../../CAPLfunctions.md) » [A429](../CAPLfunctionsA429Overview.md) » a429StopTx

# a429StopTx

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword a429StopTx( a429word myA429word );
```

## Description

This function is necessary to stop the cyclic transmission of an ARINC word in the hardware scheduler. The function modifies the selector [TxCtrl](../CAPLfunctionsA429Selectors.md).

## Parameters

- **myA429word**: ARINC word

## Return Values

- **0**: could not modify TxCtrl
- **1**: TxCtrl successfully set to CYCLIC_OFF

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)