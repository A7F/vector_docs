[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOperatorAcknowledgeStartOfMotion.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOperatorAcknowledgeStartOfMotion

# Iso11783IL_TIMOperatorAcknowledgeStartOfMotion

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMOperatorAcknowledgeStartOfMotion( ); // form 1
long Iso11783IL_TIMOperatorAcknowledgeStartOfMotion(dbNode server); // form 2
```

## Description

Performs an operator acknowledgment to start motion.

If the server supports facility **Start vehicle motion** and property **requireAcknowledgeOfStartOfMotion** is set to 1 ([Iso11783IL_TIMSetProperty](CAPLfunctionIso11783ILtimSetProperty.md)) then the function `Iso11783IL_TIMOperatorAcknowledgeStartOfMotion` must be called before the client can start its movement.

An operator acknowledgment to start motion has to be performed once after the TIM server is activated.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **Other**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
