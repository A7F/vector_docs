[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionSCCSLACGenerateNID.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SLACGenerateNID

# SLACGenerateNID

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
MethodReturnValueType SLACGenerateNID (byte NMK[], byte NID_out[]);
```

## Description

Generates a matching NID for a given NMK to the output buffer. Doesn't affect the internal state.

## Parameters

- **NMK**: Network Membership Key (16 byte).
- **NID_out**: Network ID (7 byte hexadecimal number).

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

```plaintext
on key 'x'
{
  byte NMK[16];
  byte NID[7];
  memcpy(NMK, $EVSE.SLAC.CM_SET_KEY_REQ.NMK);
  EVSE.SLACGenerateNID.Call(NMK, NID);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)