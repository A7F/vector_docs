[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDsetvalue.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783PDDSetValue

# Iso11783PDDSetValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDSetValue( dword ecuHandle, dbSignal signal, dword elementNumber, float alue );
long Iso11783PDDSetValue( dword ecuHandle, dword ddi, dword elementNumber, float value );
```

## Description

Sets the value of a process variable.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must previously have been created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **signal**: Signal from the database. The attribute `ddi` must have been defined for the signal. The signal must be defined in the same database as the node!
- **ddi**: Data Dictionary Identifier, 0x0000.0xFFFF
- **elementNumber**: Element number, 0x000.0xFFF
- **value**: New value of the process variable

## Return Values

[error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
Iso11783PDDSetValue( Sprayer, 0x200. 3, value );
Iso11783PDDSetValue( Sprayer, 0x200. 4, value );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)