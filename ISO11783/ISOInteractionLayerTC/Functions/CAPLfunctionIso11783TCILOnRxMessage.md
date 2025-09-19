[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILOnRxMessage.md)

CAPL Functions » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_OnRxMessage

# TCIL_OnRxMessage (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_OnRxMessage( pg * rxPG );
```

## Description

This callback function is called from the TC IL if the TC IL receives the parameter group, namely **before** the parameter group is processed by the TC IL. The message data can be manipulated in the callback method or handling of the message by the IL can be suppressed.

**Usage**

- To ignore some incoming messages;
- To simulate faulty behavior of the node that communicates with simulated node (by manipulating of incoming messages);

## Parameters

- **rxPG**: Message which is received

## Return Values

- **0**: Received parameter group will be ignored by the TC IL
- **1**: Received parameter group will be processed by the TC IL

## Example

The following example blocks the RQST of the pgn = 0x5** (case 5) and replace the RQST of the pgn = 0x3** by the RQST of the pgn = 0x4** (case 3).

```plaintext
long TCIL_OnRxMessage( pg * rxPG )
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

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
