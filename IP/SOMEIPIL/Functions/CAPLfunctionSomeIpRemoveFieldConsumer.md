[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveFieldConsumer.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpRemoveFieldConsumer**

# SomeIpRemoveFieldConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpRemoveFieldConsumer( dword cfHandle );
```

## Description

Removes a Field from a Consumed Service Instance. The Field was previously added by [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md).

Afterwards, the callback registered with [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md) is no longer called.

## Parameters

- **cfHandle**: Handle of the field that was created by [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
variables
{
  CONST DWORD FieldNotificationID = 30;
  CONST DWORD FieldGetterID = 31;
  CONST DWORD FieldSetterID = 32;
  DWORD aep; // Application Endpoint handle
  DWORD csi; // consumed Service Instance handle
  DWORD ceg; // consumed Eventgroup handle
  DWORD cfHandle; // consumed field handle
  DWORD gMcGetter; // getter method call
  DWORD gMcSetter; // setter method call
}

on start()
{
  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,12,1);
  // create Eventgroup
  ceg = SomeIpAddConsumedEventGroup(csi,300);
  // create field consumer as well as getter and setter method calls
  cfHandle = SomeIpCreateFieldConsumer(csi,FieldNotificationID,FieldGetterID,FieldSetterID,"OnFieldNotification");
  gMcGetter = SomeIpCreateMethodCall(csi,FieldGetterID,"OnFieldGetterResponse");
  gMcSetter = SomeIpCreateMethodCall(csi,FieldSetterID,"OnFieldSetterResponse");
}

void OnFieldNotification(DWORD pfHandle,DWORD messageHandle)
{
  write ("Field Notification Received");
  // do something here
}

void OnFieldGetterResponse(dword methodCallHandle, dword messageResponseHandle )
{
  write ("Field Getter Response Received");
  // do something here
}

void OnFieldSetterResponse(dword methodCallHandle, dword messageResponseHandle )
{
  write ("Field Setter Response Received");
  // do something here
}

on key 'g'
{
  // call getter method
  SomeIpCallMethod(gMcGetter);
}

on key 's'
{
  // set value of field content (field has common data type so no value path is needed)
  SomeIpSetValueDWord(gMcSetter,"",200);
  // call setter method
  SomeIpCallMethod(gMcSetter);
}

on key 'r'
{
  SomeIpRemoveFieldConsumer (cfHandle);
}
```

[See Also](javascript:void(0);)

```markdown
- [SomeIpAddConsumedEventGroup](CAPLfunctionSomeIpAddConsumedEventGroup.md#aanchor18667)
- [SomeIpCallMethod](CAPLfunctionSomeIpCallMethod.md#aanchor22493)
- [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md#aanchor6317)
- [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md#aanchor25251)
- [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md#aanchor15734)
- [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md#aanchor19232)
- [SomeIpReleaseConsumedServiceInstance](CAPLfunctionSomeIpReleaseConsumedServiceInstance.md#aanchor962)
- [SomeIpRemoveConsumedEventGroup](CAPLfunctionSomeIpRemoveConsumedEventGroup.md#aanchor1721)
- [SomeIpRemoveEventConsumer](CAPLfunctionSomeIpRemoveEventConsumer.md#aanchor4282)
- [SomeIpRemoveFieldConsumer](#aanchor13567)
- [SomeIpRemoveMethodCall](CAPLfunctionSomeIpRemoveMethodCall.md#aanchor15404)
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
