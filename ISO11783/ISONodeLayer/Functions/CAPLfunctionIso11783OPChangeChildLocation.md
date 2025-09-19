[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPChangeChildLocation.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPChangeChildLocation

# Iso11783OPChangeChildLocation

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeChildLocation( dword ecuHandle, 
 dword parentID, dword objectID, long dx, long dy );
```

## Description

The function moves an object. The object is moved relative inside the parent object. A **Change Child Location** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **parentID**: Parent object
- **objectID**: Object ID of the object which should be moved
- **dx**: Move X position relative by this value [pixel]
- **dy**: Move Y position relative by this value [pixel]

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
// move object 5 pixels to the right
Iso11783OPChangeChildLocation( handle, 1000, 1200, 5, 0 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
