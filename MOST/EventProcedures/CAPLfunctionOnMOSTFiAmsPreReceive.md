[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostFiAmsPreReceive

# OnMostFiAmsPreReceive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long OnMostFiAmsPreReceive(mostAmsMessage * msg);
```

## Description

When fault injection is active, this function is called before the simulation node (CAPL program or node layer module) receives the AMS message. This allows incoming messages to be manipulated in order to emulate faulty application behavior.

The message can be suppressed (return value 0), forwarded (return value 1), or forwarded as an altered message (use of [mostFiAmsReceive](../Functions/CAPLfunctionMOSTFiAmsReceive.md)).

**Note**

- All CAPL functions are available within the callback. When [output(mostAmsMessage)](../Functions/CAPLfunctionMOSToutput.md) and [mostFiAmsReceive](../Functions/CAPLfunctionMOSTFiAmsReceive.md) are used, attention must be paid that recursions are not programmed. This can be ensured through appropriate message filtering (see example below).
- The callback is only called for the AMS messages for which the simulation node has implemented a mostAmsMessage handler (i.e., for the messages whose receipt the node is intended for).

## Parameters

- **msg**: This variable contains the AMS message of the simulation node to be received. The number of transmitted data can be up to 65535 bytes for a mostAmsMessage. For reasons of efficiency, only the first 200 bytes are copied to the `msg` variable. To facilitate access to all the message's user data, the message can be assigned to an AMS message declared with a sufficient size (see example below).

## Return Values

The return value can be used to control whether or not the message is to be received by the simulation node.

- 0: Original message is not received.
- 1: Original message is received without alteration

## Example

```plaintext
// change all Set operations to SetGet operations
// before the simulation node receives the message
long OnMostFiAmsPreReceive(mostAmsMessage * msg)
{
    // The following if statement prevents this code from being called recursively
    // e.g. by ignoring the Tx acknowledgments
    if((msg.OpType == 0x0) && (msg.dir == Rx)) // Set message
    {
        // make a copy
        mostAmsMessage * modMsg = {DLC = 1000}; // buffer for 1000 data bytes
        modMsg = msg; // at most 1000 data bytes are copied here

        // modify OpType
        modMsg.OpType = 0x2;
        // forward modified message to simulation node
        mostFiAmsReceive(modMsg);

        // do not forward the original message
        return 0;
    }
    else
    {
        // forward the original message
        return 1;
    }
}
```

[OnMostFiAmsPreSend](CAPLfunctionOnMOSTFiAmsPreSend.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
