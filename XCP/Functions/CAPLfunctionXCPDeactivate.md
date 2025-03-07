[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPDeactivate.md)

**CAPL Functions** » **XCP** » **xcpDeactivate**

# xcpDeactivate

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long xcpDeactivate (char namespace[], char variable[]); // form 1`
- `long xcpDeactivate (sysvar sysvar); // form 2`

## Description

Upload and DAQ measurement will be deactivated.

**Note**  
Using system variables [structs](../../../Shared/CAPL/General/Structures.md), the function must be used for the variable valid for the entire struct but not for single members.

## Parameters

- **namespace**: Namespace of the corresponding system variable.
- **variable**: Name of the corresponding system variable.
- **sysvar**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: OK
- **-1**: System variable was not found
- **-2**: Operation not allowed

## Example

—

[xcpActivate](CAPLfunctionXCPActivate.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)