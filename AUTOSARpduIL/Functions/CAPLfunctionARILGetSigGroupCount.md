[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILGetSigGroupCount.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILGetSigGroupCount**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)