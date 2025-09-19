[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILClearAllDTCs.md)

## J1939ILClearAllDTCs

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILClearAllDTCs

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long J1939ILClearAllDTCs(); // form 1`
- `long J1939ILClearAllDTCs(dbNode node); // form 2`

### Description

This function clears the list of active DTCs, the list of previously active DTCs and all DTCs added by [J1939ILAddDTC](CAPLfunctionJ1939ILAddDTC.md).

### Parameters

- **node**: Simulation node to apply the function.

### Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
