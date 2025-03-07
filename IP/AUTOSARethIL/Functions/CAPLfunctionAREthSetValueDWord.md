[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetValueDWord.md)

# AREthSetValueDWord

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthSetValueDWord

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSetValueDWord( dword objectHandle, char valuePath[], dword value );
```

## Description

This function can be used to set a raw value in the object specified in the **objectHandle** parameter. The value is accessed in this case via symbolic access paths.

**Note**

- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL object, which must be completely described in the AUTOSAR database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Access path of the value to be set.

- **value**: Raw Value

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```c
void Initialize()
{
  dword aep; // application endpoint handle
  dword psi; // provided service handle
  dword peg; // provided eventgroup handle
  dword pev; // provided event handle

  // open application endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create service instance
  psi = AREthCreateProvidedServiceInstance(aep,10,1);

  // create eventgroup
  peg = AREthAddProvidedEventGroup(psi,1);

  // create event and add event to eventgroup
  pev = AREthAddEvent(psi, 1, "OnPrepareEvent1");
  AREthAddEventToEventgroup(peg, pev);

  // ensure that event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(dword eventHandle, dword messageHandle)
{
  // this function is called before the event is sent. Parameters
  // can be specified here.
  // set parameter "value1" of struct "param1"
  AREthSetValueDWord(messageHandle,"param1.value1",7);
}
```

[See Also](javascript:void(0);)