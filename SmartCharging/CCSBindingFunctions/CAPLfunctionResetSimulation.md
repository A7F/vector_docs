[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionResetSimulation.md)

# ResetSimulation

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » ResetSimulation

Valid for:  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType ResetSimulation ( )`

## Description

This function resets all changes made to the Binding internal data objects like StateMachine, socket states and so on.

For resetting any distributed object members e.g. messages please see [resetDistObjValues](../../DistributedObjects/Functions/CAPLfunctionResetDistObjValues.md).

## Parameters

—

## Return Values

### MethodReturnValueType

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0` OK
- `1` InvalidArgument
- `2` NoMatchingElementFound
- `3` UnknownError

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
