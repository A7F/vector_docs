[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPSetProperty.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPSetProperty

# Iso11783OPSetProperty

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetProperty( dword ecuHandle, char propertyName[], long newValue );
```

## Description

The function sets a property of the Object Pool API, i.e. the supported Virtual Terminal version.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **propertyName**: Key of the information to set:
  - **Version**: Supported version of the ISO11783 Virtual Terminal specification. Supported values: 2, 3 (default), 4 and 5. If used, the version value obtained from the database (node attribute ISO11783OPVersion) is overwritten.
  - **DebugLevel**: Controls the output to the Write Window. Supported values:
    - 0: No output
    - 1: Only errors
    - 2: Warnings and errors
    - 3: Information, warnings and errors
  - **SendPreferredAssignmentEvenIfEmpty**: Enforces sending of the **Preferred Assigning** message to the Virtual Terminal, even if no of auxiliary function has a preferred assigned auxiliary input. Supported values:
    - 0: **Preferred Assigning** message is sent to the Virtual Terminal if at least one preferred assignment exists
    - 1: **Preferred Assigning** message is sent to the Virtual Terminal even if no preferred assignment exists

- **newValue**: New value for the parameter

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)
- **-102**: Invalid parameter
- **-1113**: Unknown property

## Example

```plaintext
Iso11783OPSetProperty( handle, "Version", 3 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
