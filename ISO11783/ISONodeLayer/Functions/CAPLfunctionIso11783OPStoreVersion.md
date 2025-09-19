[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPStoreVersion.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPStoreVersion

# Iso11783OPStoreVersion

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPStoreVersion( dword ecuHandle, char versionName[] );
```

## Description

The function stores the current object pool on the Virtual Terminal. A **Store Version** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **versionName**: Name which is used to store the object pool. For [VT version](CAPLfunctionIso11783OPSetProperty.md) smaller than 5 the name must be 7 characters long. For VT version 5 and higher a name with more than 7 characters is sent with the **Store Extended Version** command.

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPStoreVersion( handle, "POOL01A" );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
