[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthCreateFieldConsumer.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthCreateFieldConsumer

# AREthCreateFieldConsumer

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
dword AREthCreateFieldConsumer( dword csiHandle, long notificationId, long getterId, long setterId, char onFieldNotificationCallback[] );
```

## Description

This function adds a Field Consumer to a Consumed Service Instance that was created by [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).

When a suitable field notification is received, the passed Notification Callback is called (see [`<OnAREthFieldNotification>`](CAPLfunctionOnAREthFieldNotification.md)).

A Field Consumer can be removed again using the [AREthRemoveFieldConsumer](CAPLfunctionAREthRemoveFieldConsumer.md) function.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance that was created with [AREthCreateConsumerServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).
- **notificationId**: Identifier of the field notification. If the field does not support a notifier, the value -1 must be specified here.
- **getterId**: Identifier of the Field Getter method. In order to call a getter method, a method must be created with the `getterId` beforehand (see also [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md) and [\`<OnAREthMethodResponse>`](CAPLfunctionOnAREthMethodResponse.md)). The method itself is then called with [AREthCallMethod](CAPLfunctionAREthCallMethod.md). If the field does not support a getter method, the value -1 must be specified here.
- **setterId**: Identifier of the Field Setter method. In order to call a setter method, a method must be created with the `setterId` beforehand (see also [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md) and [\`<OnAREthMethodResponse>`](CAPLfunctionOnAREthMethodResponse.md)). The method itself is then called with [AREthCallMethod](CAPLfunctionAREthCallMethod.md). If the field does not support a setter method, the value -1 must be specified here.
- **onFieldNotificationCallback**: This callback function is called when the Field Notification message is received.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created Field Consumer.

## Example

In this example, it is assumed that the utilized field is contained in the FIBEX database that is assigned to the CANoe configuration. The field has the **Notification ID** 30, the **Getter ID** 31, and the **Setter ID** 32. The data type of the field is a standard data type (for example, UINT8).

```plaintext
variables
{
  dword gMcGetter; // getter method call
  dword gMcSetter; // setter method call
}

void Initialize()
{
  CONST dword FieldNotificationID = 30;
  CONST dword FieldGetterID       = 31;
  CONST dword FieldSetterID       = 32;
  dword aep; // Application Endpoint handle
  dword csi; // consumed Service Instance handle
  dword ceg; // consumed Eventgroup handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,12,1);

  // create Eventgroup
  ceg = AREthAddConsumedEventGroup(csi,300);

  // create field consumer as well as getter and setter method calls
  AREthCreateFieldConsumer(csi,FieldNotificationID,FieldGetterID,FieldSetterID,"OnFieldNotification");
  gMcGetter = AREthCreateMethodCall(csi,FieldGetterID,"OnFieldGetterResponse");
  gMcSetter = AREthCreateMethodCall(csi,FieldSetterID,"OnFieldSetterResponse");
}

void OnFieldNotification(dword pfHandle,dword messageHandle)
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
  AREthCallMethod(gMcGetter);
}

on key 's'
{
  // set value of field content (field has common data type so no value path is needed)
  AREthSetValueDWord(gMcSetter,"",200);

  // call setter method
  AREthCallMethod(gMcSetter);
}
```

[See Also](javascript:void(0);)
