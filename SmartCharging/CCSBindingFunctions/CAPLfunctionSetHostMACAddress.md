[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionSetHostMACAddress.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SetHostMACAddress

# SetHostMACAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType SetHostMACAddress ( byte macAddress[] )
```

## Description

To simulate a PLC chip, the CCS Binding offers the option of sending the following three messages. For this purpose, it is recommended to create a separate communication participant that serves as a PLC chip simulation and sends the corresponding messages to the host. This method must first be called before to define the destination mac address of the messages.

PLC chip messages:

- CM_SET_KEY_CNF
- VS_HOST_ACTION_IND
- CM_ATTEN_PROFILE_IND

## Parameters

- **macAddress**: Destination mac address of the mentioned three messages.

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
  byte hostMAC[6] = {0x02, 0x00, 0x00, 0x00, 0xFF, 0x01};
  EVSE2.SetAdHocSendingEnabled.Call(1);
  EVSE2.SetHostMACAddress.Call(hostMAC);
  $EVSE2.SLAC.CM_SET_KEY_Confirmation.SetKeyResult = 0x01;
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
