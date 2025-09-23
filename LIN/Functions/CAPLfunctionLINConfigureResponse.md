[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINConfigureResponse.md)

**CAPL Functions** » **LIN** » **linConfigureResponse**

# linConfigureResponse

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `dword linConfigureResponse(dword frameId, dword dlc, byte[] responseData); // form 1`
- `dword linConfigureResponse(linFrame frame); // form 2`

## Description

Configures a response frame of a LIN node if no database is used.

**Note:** This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **frameId**: ID of the LIN frame which will be configured as response. Value range: 0..63
- **dlc**: Number of data bytes contained in the frame (Data Length Code). Value range: 0..8
- **responseData**: An array of bytes which contains the response data to be set.
- **frame**: The LIN frame which will be configured as response.

## Return Values

Returns **1** if the configuration of the response succeeded, otherwise **0**.

## Example

```plaintext
// Configure the LIN frame with the ID 0x01 as response of the slave and initialize the value of all response bytes to zero.

on preStart

{
  long i;
  byte responseData [8];

  for(i = 0; i < 8; i++)
  {
    responseData [i] = 0;
  }

  linConfigureResponse(0x01, 8, responseData);
}
```

[linConfigureResponseRange](CAPLfunctionLINConfigureResponseRange.md)
