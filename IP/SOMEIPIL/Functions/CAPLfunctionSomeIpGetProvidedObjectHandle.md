[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetProvidedObjectHandle.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpGetProvidedObjectHandle

# SomeIpGetProvidedObjectHandle

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
DWORD SomeIpGetProvidedObjectHandle( char objectSymbolicQualifier[] );
```

## Description

Enables to search for a provided object which has been created separately.

## Parameters

- **objectSymbolicQualifier**: Symbolic qualifier identifying uniquely a FIBEX 4.1 database object. For syntax see [Symbolic Database Access by SOME/IP](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPConfigFromDataBase.md).

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the looked for object.

## Example

```plaintext
on start
{
  // That the following code works there must be in the FIBEX 4.1
  // database a node providing under an unreliable endpoint
  // (UDP socket) the following objects:
  //  - A service instance named "Service_Test"
  //  - An event group named "All" belonging to "Service_Test"
  //  - An event named "Event_Test" belonging to "All"
  //  - A field named "Field_Test" belonging to "All" and having a notifier, a getter and a setter
  //  - A node consuming the event group "All"

  DWORD psi; // provided service instance handle
  DWORD peg; // provided event group handle
  DWORD pev; // provided event handle
  DWORD pfNotifier; // provided field notifier handle
  DWORD pfGetter; // provided field getter handle
  DWORD pfSetter; // provided field setter handle

  // Get handle of the provided service instance named "Service_Test"
  psi = SomeIpGetProvidedObjectHandle("Service_Test");

  // Get handle of the provided event group named "All"
  peg = SomeIpGetProvidedObjectHandle ("Service_Test::All");

  // Modifiy the unicast/multicast threshold that for one 
  // subscriber the event and field notification are sent
  // per unicast
  SomeIpSetProperty(peg,"UnicastLimit", 1);

  // Get handle of the provided event "Event_Test"
  pev = SomeIpGetProvidedObjectHandle ("Event_Test");

  // Sent the provided event "Event_Test" cyclically every 1 s
  SomeIpSetProperty(pev,"CycleTimeMs",1000);

  // Get handle of the provided field notification named "Field_Test"
  pfNotifier = SomeIpGetProvidedObjectHandle ("Field_Test");

  // Sent the providedfield notification named "Field_Test" cyclically every 2 s
  SomeIpSetProperty(pfNotifier,"CycleTimeMs",2000);

  // Get handle of the provided field getter named "Field_Test"
  pfGetter = SomeIpGetProvidedObjectHandle ("get_Field_Test");

  // Register a CAPL callback for this getter request
  SomeIpRegisterCallback(pfGetter, "OnSomeIpFieldGetterRequest");

  // Get handle of the provided field setter named "Field_Test"
  pfSetter = SomeIpGetProvidedObjectHandle ("set_Field_Test");

  // Register a CAPL callback for this setter request
  SomeIpRegisterCallback(pfSetter, "OnSomeIpFieldSetterRequest");
}

void OnSomeIpFieldGetterRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  write ("Field getter request received");
  // do something here
}

void OnSomeIpFieldSetterRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  write ("Field setter request received");
  // do something here
}
```

[See Also](javascript:void(0);)
```markdown