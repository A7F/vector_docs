[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPChangePriority.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783OPChangePriority

# Iso11783OPChangePriority

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangePriority( dword ecuHandle, dword maskID, dword priority );
```

## Description

The function changes the priority of an alarm mask. A **Change Priority** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **maskID**: Object ID of an alarm mask
- **priority**: Priority of the alarm mask

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangePriority( handle, 1200, 2 );
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
