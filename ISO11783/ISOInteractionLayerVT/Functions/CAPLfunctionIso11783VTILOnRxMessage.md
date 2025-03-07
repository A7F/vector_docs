[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnRxMessage.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_OnRxMessage**

# VTIL_OnRxMessage (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_OnRxMessage( pg * rxPG );
```

## Description

This callback function is called from the VT IL if the VT IL receives the parameter group, namely **before** the parameter group is processed by the VT IL. The message data can be manipulated in the callback method or handling of the message by the IL can be suppressed.

**Usage**

- To ignore some incoming messages;
- To simulate faulty behavior of the node that communicates with simulated node (by manipulating of incoming messages);

## Parameters

- **rxPG**: Message which is received

## Return Values

- **0**: Received parameter group will be ignored by the VT IL
- **1**: Received parameter group will be processed by the VT IL

## Example

The following example blocks the RQST of the pgn = 0x5** (case 5) and replace the RQST of the pgn = 0x3** by the RQST of the pgn = 0x4** (case 3).

```plaintext
long Iso11783IL_OnRxMessage( pg * rxPG )
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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)