[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthIsOptional.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthIsOptional**

# AREthIsOptional

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthIsOptional(dword objectHandle, char memberPath[]);
```

## Description

This function can be used to read out if a parameter or member of the object, specified in the **objectHandle** parameter, is optional or mandatory. The value is accessed in this case via symbolic access paths.

## Parameters

- **objectHandle**: Handle to an AUTOSAR Eth IL object, which must be completely described in the FIBEX database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **memberPath**: Access path of the parameter or member to be read out.

## Return Values

- **0**: If parameter or member is mandatory
- **1**: If parameter or member is optional

## Example

```plaintext
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
  WORD isOpt; // return value if parameter or member is optional
  // this function is called before the event is sent. Parameters
  // can be specified here.
  // set parameter "value1" of struct "param1" only if it is mandatory

  // get if member is optional or mandatory
  isOpt = AREthIsOptional(messageHandle,"param1.value1");

  if(isOpt == 0)
  {
    AREthSetValueDWord(messageHandle,"param1.value1",7);
  }
}
```

[See Also](javascript:void(0);)
- AREthGetData
- AREthIsOptional
- AREthSerializeMessage
- AREthSetData
- SomeIpIsOptional

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
