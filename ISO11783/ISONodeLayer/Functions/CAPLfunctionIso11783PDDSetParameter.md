[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDSetParameter.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDSetParameter

# Iso11783PDDSetParameter

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function with all possible parameter (except the case with paramName = "debug") is not effective if called before calling [Iso11783PDDLoadDeviceDescription](CAPLfunctionIso11783PDDloaddevicedescription.md).

## Function Syntax

```plaintext
long Iso11783PDDSetParameter( dword ecuHandle, char paramName[], float paramValue );
```

## Description

Changes an internal parameter of the PDD API.

## Parameters

- **ecuHandle**  
  Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) beforehand or ZERO for general parameters.

- **paramName**  
  - **"debug"**: activates debug outputs in the Write Window
    - 1: on
    - 0: off
  - **"autoUpdateVariable"**: process variable is updated if value command is received
    - 1: auto update
    - 0: process variable has to be updated manually by [Iso11783PDDSetValue](CAPLfunctionIso11783PDDsetvalue.md) e.g. in callback function [Iso11783PDDOnDataChanged](CAPLfunctionIso11783PDDOnDataChanged.md)
  - **"version"**: supported version of the ISO11783 specification: 1,2 (default), 3, and 4

- **paramValue**  
  New value for the parameter

## Return Values

- **0**  
  Process data dictionary has been created successfully

- **< 0**  
  [Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDSetParameter( ecuHandle, "debug", 1 ) == 0) {
  write( "Debug mode activated" );
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)