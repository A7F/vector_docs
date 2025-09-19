[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPLoadVersion.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPLoadVersion

# Iso11783IL_OPLoadVersion

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPLoadVersion( char versionName[] ); // form 1
long Iso11783IL_OPLoadVersion( dbNode implement, char versionName[] ); // form 2
```

## Description

The function loads an object pool, which is stored on the Virtual Terminal. A **Load Version** command is sent to the Virtual Terminal.

## Parameters

- **versionName**: designator of the version
  - For [VT version](CAPLfunctionIso11783ILOPSetProperty.md) smaller than 5 the name must be 7 characters long. For VT version 5 and higher a name with more than 7 characters is sent with the **Load Extended Version** command.
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPLoadVersion("POOL01A");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
