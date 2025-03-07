[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionBindingError.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » bindingError

# bindingError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

bindingError

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

—

## Description

The `bindingError` expression refers to a singleton object that can be used to programmatically detect errors in the [binding of distributed objects](../../../CANoeCANalyzer/CommunicationConcept/CCDistributedObjects.md#BMBindings). The object has a **valueHandle** type, which means that it has to be dereferenced to access its value.

## Parameters

—

## Selectors

- **ErrorCode**: Error code of the binding error, `valueHandle int32`, Read only
- **SubErrorCode**: Suberror code of the binding error, `valueHandle optional<long>`, Read only
- **BindingType**: Type of binding where the error occurred, `valueHandle string`, Read only
- **ErrorMessage**: Message of the error, `valueHandle string`, Read only
- **Object**: Object for which the binding failed, `valueHandle optional<string>`, Read only

## Example

```plaintext
on value_update bindingError
{
  write("binding error: %d, (%d, %d), %s, %s, (%d, %s)", $this.ErrorCode,
        $this.SubErrorCode.IsValid,
        $this.SubErrorCode,
        $this.BindingType,
        $this.ErrorMessage,
        $this.Object.IsValid,
        $this.Object);
}

on key 'a'
{
  writeToLog("binding error: %d, %s", $bindingError.ErrorCode, $bindingError.ErrorMessage);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)