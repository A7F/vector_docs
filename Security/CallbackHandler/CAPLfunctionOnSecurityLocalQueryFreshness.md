# OnSecurityLocalQueryFreshness

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces OnLocalSecurityQueryLocalFreshness.

## Function Syntax

```
long OnSecurityLocalQueryFreshness(dword context, char pduName[], dword dataId, dword freshnessValueId, dword attemptNr, byte payload[], dword payloadLength, qword& freshness, dword& freshnessLength, qword truncatedRxFreshness, dword truncatedRxFreshnessBitLength)
```

## Description

This callback is called for every secured PDU for which a MAC has to be calculated or verified. The callback is triggered before the MAC calculation starts. It provides the possibility to calculate a freshness value in CAPL and force the Security Manager to use this freshness value for the next MAC calculation/verification.

## Parameters

- **dword context**  
  - 1: PDU is received (MAC verification)
  - 0: PDU is transmitted (MAC calculation)

- **char pduName[]**  
  The name of the PDU.

- **dword dataId**  
  The data ID of the PDU.

- **dword freshnessValueId**  
  The freshness value ID of the PDU.

- **dword attemptNr**  
  The number of the attempted verification.

- **byte payload[]**  
  The payload of the PDU.

- **dword payloadLength**  
  The payload length of the PDU in bytes.

- **qword& freshness [Out]**  
  The freshness the CAPL code provides.

- **dword& freshnessLength [Out]**  
  The freshness length of the freshness the CAPL code provides in bits.

- **qword truncatedRxFreshness**  
  The received freshness (only in case context is 1).

- **dword truncatedRxFreshnessBitLength**  
  The received freshness length in bits (only in case context is 1).

## Return Values

- **qword& freshness [Out]**  
  The freshness the CAPL code provides.

- **dword& freshnessLength [Out]**  
  The freshness length of the freshness the CAPL code provides in bits.

- **long: 0**  
  No freshness is provided by this callback.

- **long: 1**  
  The freshness and freshnessLength shall be used for MAC calculation/verification.

## Example

**Example 1**

```c
// Example 1:
// implement this callback at the transmitting node of the pdu
// This example shows how to specify an older or newer freshness value, the MAC will be "correct" but the freshness is "wrong" (compared to the freshness of the system)
long OnSecurityLocalQueryFreshness(
  dword context,
  char pduName[],
  dword dataId,
  dword freshnessValueId,
  dword attemptNr,
  byte payload[],
  dword payloadLength,
  qword& freshness,
  dword& freshnessLength,
  qword truncatedRxFreshness,
  dword truncatedRxFreshnessBitLength)
{
  long result = 0;
  char idString[2] = "";
  dword idValue;
  BYTE freshnessValue[6];
  dword freshnessValueLength;

  // filter for tx pdus (tx = 0; rx = 1)
  if (context != 0)
  {
    return 0; // use internal freshness model
  }

  // filter for the correct data id to influence
  if (dataId != 0)
  {
    return 0; // use internal freshness model
  }

  // now get the freshness currently stored in the internal freshness model
  // the following parameter size and values are depending on the selected Security Profile.
  // Please refer to the Security Source Manual to get more detailed information
  // about parameter values, identifier and freshness value layouts.

  idValue = 0;
  freshnessValueLength= 6;
  result = SecurityLocalGetFreshness("", idValue, freshnessValue, freshnessValueLength);

  // change the freshness value
  freshnessValue[5] = 0xFF;

  // write the new Freshness value back.
  // the last parameter is currently reserved and shall be set to 0
  result = SecurityLocalSetFreshness("", idValue, freshnessValue, freshnessValueLength, 0);

  // as Set and Get Freshness is changing the internal freshness model, return 0
  return 0;
}
```

**Example 2**

```c
// Example 2:
// This example shows how to provide a USER based freshness value
long OnSecurityLocalQueryFreshness(
  dword context,
  char pduName[],
  dword dataId,
  dword freshnessValueId,
  dword attemptNr,
  byte payload[],
  dword payloadLength,
  qword& freshness,
  dword& freshnessLength,
  qword truncatedRxFreshness,
  dword truncatedRxFreshnessBitLength)
{
  if ((dataId == 1) && (context == 0)) // check for PDU with data ID and
  context [(0 = tx) (1 = rx)] to specify a freshness for
  {
    freshness = 7; // new Freshness Value
    freshnessLength = 64; // new freshness length

    return 1; // use my values
  }
  return 0; // for all others use internal calculated freshness values
}
```
