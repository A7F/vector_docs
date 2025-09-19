# getPayloadData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
getPayloadData(errorframe errFrame, byte[] payload, dword payloadSize;
```

## Description

Returns the valid payload of a frame that was interrupted during transmission.

Depending on error position valid bits are written to the payload parameter. If there is no payload data, nothing is written into the payload parameter.

## Parameters

- **errFrame**: Error frame which includes the payload.
- **payload**: Array for writing the transmitted payload of the error frame.
- **payloadSize**: Size of the payload parameter.

## Return Values

- **0**: No valid payload.
- **>0**: Count of valid bits within the payload array.

## Example

```plaintext
variables
{
  byte payload[64];
  dword validBits;
}

on errorFrame
{
  int i = 0;
  byte validPayload[64];

  validBits = getPayloadData(this, validPayload, elcount(validPayload));
  byteCount = validBits / 8;
  bitCount = validBits % 8;

  dataLength =  dlcToDataLength[this.DLC];

  for(i = 0; i < byteCount; ++i)
  {
    payload[i] = this.byte(i);
  }
}
```
