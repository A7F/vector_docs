[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDChangeDesignator.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDChangeDesignator

# Iso11783PDDChangeDesignator

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDChangeDesignator( dword ecuHandle, word objectID, char asciiDesignator[] );
long Iso11783PDDChangeDesignator( dword ecuHandle, word objectID, char asciiDesignator[], byte encoding );
```

## Description

The function sends a Change Designator message with a new object designator to the Task Controller.

The first variant converts the ASCII designator string to an UTF-8 string if the supported version is 2 or higher.

In the second variant you can specify if the designator string shall be encoded to UTF-8 or not.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) beforehand or ZERO for general parameters.
- **objectID**: ID of the object.
- **asciiDesignator**: New object designator.
- **encoding**: Specifies if the designator is encoded before it is transmitted or not
  - 0: designator string is not encoded
  - 1: designator string is encoded to UTF-8

## Return Values

[error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

**Example 1**

```plaintext
if (Iso11783PDDChangeDesignator( ecuHandle, 1, "myNewDesignator" ) == 0) {
  write( "Change Designator command is sent successfully" );
}
```

**Example 2 (avoid encoding because string is already UTF-8 string encoded)**

```plaintext
char euroSign[255];
euroSign.byte(0) = 0xE2;
euroSign.byte(1) = 0x82;
euroSign.byte(2) = 0xAC;
euroSign.byte(3) = 0;

if (Iso11783PDDChangeDesignator( ecuHandle, 1, euroSign, 0 ) == 0) {
  write( "Command to change designator to '€' is sent successfully" );
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
