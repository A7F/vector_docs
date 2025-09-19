# monitoringDistObjMethodRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
monitoringDistObjMethodRef <Member>
```

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

—

## Description

References a monitoring distributed object method member. This type cannot be used in declarations. This is a subtype of `monitoringDistObjMemberRef <Member>`.

## Parameters

- **Member**: Path of a monitoring distributed object method member.

## Selectors

- **LatestCall**: Struct with values of the in-parameters in the latest call.  
  - Type: `valueHandle <struct depending on signature>`
  - Access Limitation: Read only

- **LatestReturn**: Struct with values of the out-parameters in the latest call.  
  - Type: `valueHandle <struct depending on signature>`
  - Access Limitation: Read only

- **ParamDefaults**: Struct with default values of the out-parameters.  
  - Type: `valueHandle <struct depending on signature>`
  - Access Limitation: Read only  
  - Note:
    - Not available for consumed members.
    - The referenced value is mutable.

- **DefaultResult**: Default result value.  
  - Type: `valueHandle <return type>`
  - Access Limitation: Read only  
  - Note:
    - Not available for consumed members.
    - The referenced value is mutable.

- **AutoAnswerMode**: Mode for automatic answering function calls.  
  - Type: `valueHandle uint32`
  - Access Limitation: Read only  
  - Note:
    - Not available for consumed members.
    - The referenced value is mutable.
  - Modes:
    - Auto (0): calls are answered with the default values.
    - OffOrManual (1): calls are not automatically answered.
    - Discard (2): calls are discarded and will not be answered.
    - AutoField (3): only for field getters and setters; use the field value to answer the call.

- **AutoAnswerTimeNS**: Time in nanoseconds until the call is answered if the **AutoAnswerMode** is **Auto** or **AutoField**.  
  - Type: `valueHandle int64`
  - Access Limitation: Read only  
  - Note:
    - Not available for consumed members.
    - The referenced value is mutable.

## Example

—

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
