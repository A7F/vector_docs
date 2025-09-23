[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetProductIdentification.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetProductIdentification

# Iso11783IL_TIMSetProductIdentification

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetProductIdentification(char identification[]); // form 1
long Iso11783IL_TIMSetProductIdentification(dbNode participant, char identification[]); // form 2
```

## Description

Sets the content of message **Product identification** (see ISO11783-12 B.10).

If the **Product identification** message is in the Tx list of the TIM node and a request for PGN 65242 (FC8Dh) is received then the **Product identification** message is sent using the data of parameter **identification**.

## Parameters

- **identification**  
  Content of the **Product information** message. Format of the string must be `<product identification code>*<product identification brand>*<product identification model>*`.  
  If this parameter is an empty string then no **Product identification information** message is sent on a request. To answer the request with another message (e.g. an **Acknowledgment** message) you can use [ISO11783IL_OnRequest](CAPLfunctionIso11783ILOnRequest.md).

- **participant**  
  TIM participant (TIM server or TIM client).

## Return Values

- **0**  
  Property has been set successfully

- **< 0**  
  An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_TIMSetProductIdentification ("1234567890ABC*Brand B*1962i*");
```
