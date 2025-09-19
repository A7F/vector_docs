# ARILGetSigGroupCount

**Valid for**: CANoe DE • CANoe4SW DE

**Note**: The function can only be called for PDUs that are potentially sent by this IL instance. (PDUs that are sent from the node, the IL is assigned to).

## Function Syntax

```c
long ARILGetSigGroupCount (char aMsgName[]);
```

## Description

Evaluates how many signal groups are defined inside the PDU.

## Parameters

- **aMsgName**: The symbolic name of a PDU in the database.

## Return Values

- **≥ 0**: The number of signal groups.
- **< 0**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—
