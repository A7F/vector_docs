[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783GetEcuState.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783GetEcuState

# Iso11783GetEcuState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783GetEcuState(dword ecuHandle);
dword Iso11783GetEcuState(dbNode dbNode);
```

## Description

Returns the current state of the ECU.

## Parameters

- **ecuHandle**: ECU handle
- **dbNode**: Node from database

## Return Values

- **0**: initialized
- **1**: claiming
- **2**: online
- **3**: offline

## Example

```plaintext
if (Iso11783GetEcuState(handle) == 2) {
  write("ECU is online");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)