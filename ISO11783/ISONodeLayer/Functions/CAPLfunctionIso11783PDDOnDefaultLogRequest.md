[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDOnDefaultLogRequest.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDOnDefaultLogRequest

# Iso11783PDDOnDefaultLogRequest (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783PDDOnDefaultLogRequest( dword ecuHandle );
```

## Description

This function can be implemented in the CAPL program. The function is called up by the node layer if default logging is requested by the Task Controller. Default logging can then be started with the CAPL function [Iso11783PDDSetLogTrigger](CAPLfunctionIso11783PDDSetLogTrigger.md).

## Parameters

- **ecuHandle**: Handle of the ECU

## Return Values

—

## Example

```c
void Iso11783PDDOnDefaultLogRequest( dword ecuHandle )
{
  Iso11783PDDSetLogTrigger ( ecuHandle, 4, 0x0100, 0, 1000 );
  Iso11783PDDSetLogTrigger ( ecuHandle, 4, 0x0101, 0, 1000 );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
