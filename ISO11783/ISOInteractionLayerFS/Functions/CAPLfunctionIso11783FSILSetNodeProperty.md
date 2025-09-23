[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILSetNodeProperty.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_SetNodeProperty**

# FSIL_SetNodeProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_SetNodeProperty( char propertyName[], long propertyValue); // form 1`
- `long FSIL_SetNodeProperty( dbNode fs, char propertyName[], long propertyValue); // form 2`
- `long FSIL_SetNodeProperty( char propertyName[],char propertyValue[]); // form 3`
- `long FSIL_SetNodeProperty( dbNode fs, char propertyName[], char propertyValue[]); // form 4`

## Description

Changes an internal property of the File Server node.

## Parameters

- **fs**: File Server simulation node to apply the function.
- **propertyName**: Name of the property (see [Functional Properties of FS IL](../CAPLfunctionsISOILFSProperties.md) and [Network Properties of FS IL](../CAPLfunctionsISOILFSNetworkProperties.md)).
- **propertyValue**: New value for the property.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2, 4

```c
void SetNodeProperties()
{
  // Set File Server version 3
  FSIL_SetNodeProperty(FS, "fsVersion", 3);
  // Set root directory for file server volumes
  FSIL_SetNodeProperty(FS, "rootDirectory", "ISOBUS_FSRootDir");
}
```
