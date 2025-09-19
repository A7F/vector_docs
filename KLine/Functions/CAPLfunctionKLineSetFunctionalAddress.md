[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetFunctionalAddress.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetFunctionalAddress

# KLine_SetFunctionalAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`long KLine_SetFunctionalAddress(Byte functionalAddress)`

## Description

Sets the functional address of the ECU, i.e. it can receive broadcast messages directed at this address.

## Parameters

- **functionalAddress**: Broadcast address used by the tester to address a group of ECUs.

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

[KLine_SetECUAddress](CAPLfunctionKLineSetECUAddress.md) • [KLine_SetTesterAddress](CAPLfunctionKLineSetTesterAddress.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
