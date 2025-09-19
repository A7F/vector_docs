[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINOutput.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » output (LIN)

# output (LIN)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void output(linFrame msg);
```

## Description

This function can be used for two purposes:

- To apply frame header on the bus, i.e. to transmit the frame. In that case RTR selector must be set to 1.

  **Note**: When LIN hardware is not in Master mode calling this function will have no effect.

- To reconfigure response data of LIN frame. In that case RTR selector must be set to 0. The LIN hardware responds to the next request of the specified frame with the newly configured data.

  **Note**: If working without a database it is necessary to configure a message in the handler [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md). The configuration is done via the output function.

## Parameters

- **Msgext**: Variable of type **linFrame**. List of available selectors for this type of objects can be found under [linFrame selectors](../Selectors/CAPLfunctionLINMessage.md).

## Return Values

—

## Example

```plaintext
linFrame MotorControl frameMotorControl;
...
// Reconfigure response of the frame defined in database 
linFrame MotorControl frameMotorControl;
frameMotorControl.RTR = 0;
frameMotorControl.byte(0)=0xDF;
frameMotorControl.byte(1)=0x20;
output(frameMotorControl);
...
// Send the frame header
frameMotorControl.RTR = 1;
output(frameMotorControl);
...
// Function to set response on channel 2 for any frame.
// The specified frame might not be defined in database.
void SetFrameResponse(byte frameID, byte frameSize)
{
    int index;
    linFrame 0x0 frame = {msgChannel=2}; // define frame object on channel 2
    // Setting frame size in runtime possible only with this function
    linSetExpectedRespLength(frameID, frameSize);
    frame.ID = frameID; // set specified frame ID
    // initialize data byte fields
    for (index=0; index < frameSize; ++index)
    {
        frame.byte(index) = 0xFF;
    }
    // issue request to update the configured response
    frame.RTR = 0;
    output(frame);
    linSetRespCounter(frameID, -1); // enable unlimited number of responses
}
...
// Configuring a message in on preStart when working without database.
linFrame 0x20 aLinMsg;
output(aLinMsg);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
