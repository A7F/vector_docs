[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINConfigureResponseRange.md)

**CAPL Functions** » **LIN** » **linConfigureResponseRange**

# linConfigureResponseRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linConfigureResponseRange(byte[] frameIds, byte[] dlcs, byte[][8] responseData)
```

## Description

Configures a range of frames as response of a LIN node if no database is used.

**Note:**

- This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).
- All of the array parameters must contain the same number of elements.

## Parameters

- **frameIds**: Array which contains the ids of every frame to be configured.  
  Valid frame id range: 0..63

- **dlcs**: Array of dlcs (Data Length Codes) which defines the number of data bytes for every frame to be configured.  
  Valid dlc range: 0..8

- **responseData**: An array which points to an array of 8 bytes which contains the initial response data to be set for every frame.

## Return Values

Returns 1 if the configuration of all given frames succeeded, otherwise 0.

## Example

```c
// Configure two LIN frames with the IDs 0x01 and 0x02 as response of the slave. The first frame contains 5 and the second one 2 data bytes.

on preStart
{
  byte ids[2] = { 0x01, 0x02 };
  byte dlcs[2] = { 5, 2 };
  byte responseData[2][8];

  responseData[0][0] =  0x55;
  responseData[0][1] =  0x55;
  responseData[0][2] =  0x55;
  responseData[0][3] =  0x55;
  responseData[0][4] =  0x55;

  responseData[1][0] =  0xAA;
  responseData[1][1] =  0xAA;

  linConfigureResponseRange(ids, dlcs, responseData);
}
```

[linConfigureResponse](CAPLfunctionLINConfigureResponse.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
