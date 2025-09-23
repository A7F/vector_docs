[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSetSendPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetSendPDU

# frSetSendPDU

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void frSetSendPDU( <PDU object> );
```

## Description

Configures the hardware to transmit the specified PDU. All relevant slots are submitted for transmission. This submission must take place in the `On preStart` routine in the transmit branch. If a frPDU object was created using [frPDU](../Objects/CAPLfunctionFrPDU.md), it can be submitted for transmission with this function.

## Parameters

- **`<PDU object>`**: Specifies the PDU object that is to be submitted for transmission.

## Return Values

—

## Example

For an example see function [frUpdatePDU](CAPLfunctionFRUpdatePDU.md).
