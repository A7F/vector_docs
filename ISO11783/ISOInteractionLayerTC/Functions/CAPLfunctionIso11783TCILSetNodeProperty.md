[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetNodeProperty.md)

**CAPL Functions » ISO11783 » Task Controller Interaction Layer (TC IL) » TCIL_SetNodeProperty**

# TCIL_SetNodeProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_SetNodeProperty( char propertyName[], long propertyValue); // form 1
long TCIL_SetNodeProperty( dbNode tc, char propertyName[], long propertyValue); // form 2
```

## Description

Changes an internal property of the node.

## Parameters

- **tc**: TC simulation node to apply the function
- **propertyName**: Name of the property (see [Functional Properties of TC IL](../CAPLfunctionsISOILTCProperties.md) and [Network Properties of TC IL](../CAPLfunctionsISOILTCNetworkProperties.md)).
- **propertyValue**: New value for the property

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```plaintext
void SetLanguageToEnglish()
{
  TCIL_SetNodeProperty(TC, "languageCode", 0x656E); // 'en'
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)