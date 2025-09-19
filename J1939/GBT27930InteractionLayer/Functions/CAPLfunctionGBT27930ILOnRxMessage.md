[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILOnRxMessage.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_OnRxMessage**

# GBT27930IL_OnRxMessage (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_OnRxMessage( pg * rxPG )
```

## Description

This callback function is called from the GBT27930 IL if the GBT27930 IL receives the parameter group, namely **before** the parameter group is processed by the GBT27930 IL. The message data can be manipulated in the callback method or handling of the message by the IL can be suppressed.

**Usage**

- To ignore some incoming messages.
- To simulate faulty behavior of the node that communicates with simulated node (by manipulating of incoming messages).

## Parameters

- **rxPG**: message which is received

## Return Values

- **0**: Received parameter group will be ignored by the J1939 Interaction Layer.
- **1**: Received parameter group will be processed by the J1939 Interaction Layer.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
