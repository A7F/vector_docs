[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783AppNmtIndication.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783AppNmtIndication

# Iso11783AppNmtIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783AppNmtIndication( long busHandle, long address, long flag );
```

## Description

This function is called when an ECU claims an address or an ECU loses its address. The function is also called if no ECU was created yet.

With [Iso11783GetRxData()](CAPLfunctionIso11783GetRxData.md) the device name can be copied to a buffer.

## Parameters

- **busHandle**: Bus handle
- **address**: Address of the ECU or Null-Address
- **flag**: Reason for calling this function:
  - 1: an ECU starts claiming, Address Claim PG received
  - 2: successfully claimed, 250 ms after Address Claim PG
  - 3: Cannot Claim Address received

## Return Values

—

## Example

```plaintext
dword Iso11783AppNmtIndication( LONG busHandle, LONG address, LONG flag )
{
  char deviceName[8];
  Iso11783GetRxData( elCount(deviceName), deviceName );
  /* user code */
  return 0;
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
