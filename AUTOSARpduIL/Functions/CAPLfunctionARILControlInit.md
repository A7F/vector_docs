[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILControlInit.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILControlInit**

# ARILControlInit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILControlInit ()
```

## Description

Initializes the IL. If this function is called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md), then the IL will enter the **suspended** state during [on Start](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) and must explicitly be started.

## Parameters

—

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlStart](CAPLfunctionARILControlStart.md) • [ARILControlStop](CAPLfunctionARILControlStop.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)