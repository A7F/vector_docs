[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctiondistObjMethodRef.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjMethodRef

# distObjMethodRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`distObjMethodRef <Member>`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [distObjMethodRef::CallAsync](../Methods/CAPLfunctiondistObjMethodRefCallAsync.md)
- [distObjMethodRef::CallAsync_Phys](../Methods/CAPLfunctiondistObjMethodRefCallAsyncPhys.md)
- [distObjMethodRef::Call](../Methods/CAPLfunctiondistObjMethodRefCall.md)
- [distObjMethodRef::Call_Phys](../Methods/CAPLfunctiondistObjMethodRefCallPhys.md)

## Description

References a distributed object method member. This type cannot be used in declarations. This is a subtype of [distObjMemberRef <Member>](CAPLfunctiondistObjMemberRef.md).

## Parameters

- **Member**: Path of a distributed object method member.

## Selectors

- **LatestCall**: Struct with values of the in-parameters in the latest call.  
  Type: `valueHandle <struct depending on signature>`  
  Access Limitation: Read only  
  *Note*: The referenced value is immutable.

- **LatestReturn**: Struct with values of the out-parameters in the latest call.  
  Type: `valueHandle <struct depending on signature>`  
  Access Limitation: Read only  
  *Note*: The referenced value is immutable.

- **ParamDefaults**: Struct with default values of the out-parameters.  
  Type: `valueHandle <struct depending on signature>`  
  Access Limitation: Read only  
  *Note*: Not available for consumed members. The referenced value is mutable.

- **DefaultResult**: Default result value.  
  Type: `valueHandle <return type>`  
  Access Limitation: Read only  
  *Note*: Not available for consumed members. The referenced value is mutable.

- **AutoAnswerMode**: Mode for automatic answering function calls.  
  Type: `valueHandle uint32`  
  Access Limitation: Read only  
  *Note*: Not available for consumed members. The referenced value is mutable.

- **AutoAnswerTimeNS**: Time in nanoseconds until the call is answered if the AutoAnswerMode is Auto or AutoField.  
  Type: `valueHandle int64`  
  Access Limitation: Read only  
  *Note*: Not available for consumed members. The referenced value is mutable.

- **CurrentCCO**: Get the current call context for the method.  
  Type: `callContext <Method>`  
  Access Limitation: Read only  
  *Note*: Not available for consumed members.

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  $object.ExampleMethodMember.AutoAnswerMode = 0;
  $object.ExampleMethodMember.AutoAnswerTimeNS = 100;
  object.ExampleMethodMember.CallAsync();
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)