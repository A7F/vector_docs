[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDChangeDesignator.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_PDDChangeDesignator

# Iso11783IL_PDDChangeDesignator

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_PDDChangeDesignator( word objectID, char designator[] ); // form 1`
- `long Iso11783IL_PDDChangeDesignator( word objectID, char designator[], byte convert ); // form 2`
- `long Iso11783IL_PDDChangeDesignator( dbNode implement, word objectID, char designator[], byte convert ); // form 3`

## Description

The function sends a **Change Designator** message with a new object designator to the Task Controller.

- Form 1 uses the current string encoding and converts the designator string to an UTF-8 string if the supported version is 2 or higher, or to an ASCII string if the supported version is 1.
- Form 2 and Form 3 allow you to specify whether the designator string is already UTF-8 encoded, or whether the designator shall be converted to UTF-8 using the current CAPL program encoding.

## Parameters

- **objectID**: ID of the object
- **designator**: new object designator
- **convert**: specifies whether or not to convert the identifier to UTF-8 before sending
  - 0: designator string shall be not converted to UTF-8 and sent as it is
  - 1: designator string shall be converted to UTF-8 (if necessary)
- **implement**: Simulation node to apply the function.

## Return Values

[error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example 1**

```plaintext
if (Iso11783IL_PDDChangeDesignator(1, "myNewDesignator") == 0) {
  write("Change Designator command is sent successfully");
}
```

**Example 2** (avoid converting because string is already UTF-8 string encoded)

```plaintext
char euroSign[255];
euroSign.byte(0) = 0xE2;
euroSign.byte(1) = 0x82;
euroSign.byte(2) = 0xAC;
euroSign.byte(3) = 0;

if (Iso11783IL_PDDChangeDesignator(1, euroSign, 0) == 0) {
  write("Command to change designator to '€' is sent successfully");
}
}
```
