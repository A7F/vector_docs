[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPDeleteVersion.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPDeleteVersion

# Iso11783IL_OPDeleteVersion

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPDeleteVersion( char versionName[] );` // form 1
- `long Iso11783IL_OPDeleteVersion( dbNode implement, char versionName[] );` // form 2

## Description

The function deletes an object pool, which is stored on the Virtual Terminal. A **Delete Version** or **Extended Delete Version** command is sent to the Virtual Terminal.

## Parameters

- **versionName**: designator of the version  
  For [VT version](CAPLfunctionIso11783ILOPSetProperty.md) smaller than 5 the name must be 7 characters long. For VT version 5 and higher a name with more than 7 characters is sent with the **Delete Extended Version** command.

- **implement**: Simulation node to apply the function.

## Return Values

- `= 0`: Function has been executed successfully
- `< 0`: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPDeleteVersion( "POOL01A" ); // results in a Delete Version command
Iso11783IL_OPDeleteVersion( "Planter 12.0.34 en" ); // results in a Extended Delete Version command
```

[Iso11783IL_OPStoreVersion](CAPLfunctionIso11783ILOPStoreVersion.md) • [Iso11783IL_OPLoadVersion](CAPLfunctionIso11783ILOPLoadVersion.md) • [Iso11783IL_OPGetVersion](CAPLfunctionIso11783ILOPGetVersion.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
