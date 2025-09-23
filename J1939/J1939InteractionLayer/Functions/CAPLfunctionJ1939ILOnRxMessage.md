[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILOnRxMessage.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILOnRxMessage

# J1939ILOnRxMessage (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILOnRxMessage( pg * rxPG )
```

## Description

This callback function is called from the J1939 IL if the J1939 IL receives the parameter group, namely **before** the parameter group is processed by the J1939 IL. The message data can be manipulated in the callback method or handling of the message by the IL can be suppressed.

**Usage**

- To ignore some incoming messages.
- To simulate faulty behavior of the node that communicates with simulated node (by manipulating of incoming messages).

## Parameters

- **rxPG**: message which is received

## Return Values

- **0**: Received parameter group will be ignored by the J1939 Interaction Layer.
- **1**: Received parameter group will be processed by the J1939 Interaction Layer.

## Example

The following example blocks the RQST of the pgn = 0x5** (case 5) and replace the RQST of the pgn = 0x3** by the RQST of the pgn = 0x4** (case 3).

```plaintext
long J1939ILOnRxMessage( pg * rxPG )
{
  if(rxPG.PGN == 0xEA00)
  {
    switch(rxPG.BYTE(1))
    {
      case 3:
        rxPG.BYTE(1) = 4;
        return 1;

      case 5:
        return 0;

      default:
        return 1;
    }
  }
  return 1;
}
```
