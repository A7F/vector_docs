[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDdelete.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDDelete

# Iso11783PDDDelete

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDDelete( dword ecuHandle );
```

## Description

Deletes the process data directory and disconnects from the Task Controller.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must previously have been created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
Iso11783PDDDelete( ecuHandle );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)