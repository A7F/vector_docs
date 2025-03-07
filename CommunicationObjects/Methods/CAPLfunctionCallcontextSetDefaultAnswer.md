[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionCallcontextSetDefaultAnswer.md)

## CAPL Functions » Communication Objects » callcontext::SetDefaultAnswer

# callcontext::SetDefaultAnswer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

```plaintext
void callContext::SetDefaultAnswer();
```

### Description

Sets the return value and the out parameters for the call to their defaults.

The values are set to their defaults on receival of a call if the **AutoAnswerMode** is set to **Auto**. You can (re)set them explicitly with this method.

You can change the defaults with the **ParamDefaults** and **DefaultResult** properties at the provider endpoint.

### Parameters

—

### Return Values

—

### Example

```plaintext
on fct_Called MirrorAdjustment.providerSide[all,LeftMirror].Adjust
{
  this.SetDefaultAnswer();
  this.SetTimeToAnswer(10);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [callcontext::SetTimeToAnswer](CAPLfunctionCallcontextSetTimeToAnswer.md) • [callcontext::ReturnCall](CAPLfunctionCallcontextReturnCall.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)