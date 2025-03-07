[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILSetEvent.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILSetEvent**

# ARILSetEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

- It is possible to ignore the transmit-model in the database and to generate the transmission event manually.
- It is strongly recommended to use this functionality only for test purposes and not in real simulations. The database should be corrected instead.

## Function Syntax

```
long ARILSetEvent (dbSignal)
```

## Description

This function considers **Debounce Delay**, and it also considers the activity of the network. So a call of this function will lead to a transmission of the associated PDU, if the network is active.

## Parameters

- **dbSignal**: The symbolic name of a signal in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILSetPDUEvent](CAPLfunctionARILSetPDUEvent.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)