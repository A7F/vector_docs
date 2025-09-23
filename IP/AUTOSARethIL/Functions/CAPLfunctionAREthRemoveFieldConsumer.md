# AREthRemoveFieldConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveFieldConsumer( dword cfHandle );
```

## Description

Removes a Field from a Consumed Service Instance. The Field was previously added by [AREthCreateFieldConsumer](CAPLfunctionAREthCreateFieldConsumer.md).

Afterwards, the callback registered with [AREthCreateFieldConsumer](CAPLfunctionAREthCreateFieldConsumer.md) is no longer called.

## Parameters

- **cfHandle**: Handle of the field that was created by [AREthCreateFieldConsumer](CAPLfunctionAREthCreateFieldConsumer.md).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

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
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,12,1);
  // create Eventgroup
  ceg = AREthAddConsumedEventGroup(csi,300);
  // create field consumer as well as getter and setter method calls
  cfHandle = AREthCreateFieldConsumer(csi,FieldNotificationID,FieldGetterID,FieldSetterID,"OnFieldNotification");
  gMcGetter = AREthCreateMethodCall(csi,FieldGetterID,"OnFieldGetterResponse");
  gMcSetter = AREthCreateMethodCall(csi,FieldSetterID,"OnFieldSetterResponse");
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
  AREthSetValueDWord(gMcSetter,"",200);
  // call setter method
  AREthCallMethod(gMcSetter);
}

on key 'r'
{
  AREthRemoveFieldConsumer (cfHandle);
}
```

[See Also](javascript:void(0);)

```markdown
