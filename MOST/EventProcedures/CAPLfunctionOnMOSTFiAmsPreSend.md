[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTFiAmsPreSend.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostFiAmsPreSend

# OnMostFiAmsPreSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long OnMostFiAmsPreSend(mostAmsMessage * msg);
```

## Description

## Parameters

- **msg**: This variable contains the send request of the simulation node. The number of transmitted data can be up to 65535 bytes for a mostAmsMessage. For reasons of efficiency, only the first 200 bytes are copied to the **msg** variable. To facilitate access to the entire message's user data, the message can be assigned to an AMS message declared with a sufficient size (see example below).

## Return Values

- `0`: Original message is not sent
- `1`: Original message is sent without alteration

## Example

```plaintext
// change all Status messages a simulated node tries to send to error messages
long OnMostFiAmsPreSend(mostAmsMessage * msg)
{
    if(msg.OpType == 0xC) // Status or Result message
    {
        // make a copy
        mostAmsMessage * modMsg = {DLC = 1000}; // buffer for 1000 data bytes
        modMsg = msg; // at most 1000 data bytes are copied here

        // modify OpType
        modMsg.OpType = 0xF;
        // keep message length and data
        // but change the first byte
        modMsg.byte(0) = 0x0B; // set ErrorCode=Device malfunction
        // send modified message
        output(modMsg);

        // do not send original message
        return 0;
    }
    else
    {
        // send original message
        return 1;
    }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
