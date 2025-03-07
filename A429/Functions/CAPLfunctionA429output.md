[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429output.md)

[CAPL Functions](../../CAPLfunctions.md) » [A429](../CAPLfunctionsA429Overview.md) » output (A429)

# output (A429)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void output( a429word myA429Word );
```

## Description

This function triggers the transfer of the myA429Word to the network interface. When the mode [Simulated bus](../../../CANoeCANalyzer/Ribbon/File/Options/Measurement/MeasurementGeneralSettings.md) is used a built-in simulation layer takes care of the ARINC word.

Note that the transmission behavior may be adjusted via the ARINC word [selectors](../CAPLfunctionsA429Selectors.md) **TxCtrl**, **gap** and **TxCycle**. If TxCtrl is already set to the value 1, the function updates the ARINC word in the hardware scheduler.

For transferring multiple ARINC words in one call, use the function [a429Transmit](CAPLfunctionA429Transmit.md).

## Parameters

- **myA429word**: ARINC word

## Example

See [Scheduling an ARINC word](../CAPLfunctionsA429Scheduling.md)

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)