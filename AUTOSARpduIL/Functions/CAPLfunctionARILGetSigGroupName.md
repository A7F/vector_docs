# ARILGetSigGroupName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The function can only be called for PDUs that are potentially sent by this IL instance. (PDUs that are sent from the node, the IL is assigned to).

## Function Syntax

```plaintext
long ARILGetSigGroupName (char aMsgName[], dword index, char sigGroupName[], long maxSigGroupNameLen);
```

## Description

Retrieves the name of the n<sup>th</sup> signal group of the PDU.

## Parameters

- **aMsgName**: The symbolic name of a PDU in the database.
- **index**: Number of the signal group (starting from **0**).
- **sigGroupName**: Returns the full name of the designated signal group.
- **maxSigGroupNameSize**: Size of the buffer for the name of the signal group.

## Return Values

- **0**: No error
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—
