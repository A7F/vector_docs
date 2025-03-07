[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOperatorAcknowledge.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOperatorAcknowledge

# Iso11783IL_TIMOperatorAcknowledge

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMOperatorAcknowledge(); // form 1
long Iso11783IL_TIMOperatorAcknowledge(dbNode server); // form 2
```

## Description

This function performs an operator acknowledgment.

It sends a **TIM_ServerStatus_Msg** message with the **Acknowledge** indication for **3** times in a row.

It changes the automation status of a TIM function to **Automation Pending** in case this TIM function is allowed for the operator acknowledgment.

## Parameters

- **server**: TIM server node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_ TIMOperatorAcknowledge();
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)