[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetProvidedObjectHandle.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthGetProvidedObjectHandle

# AREthGetProvidedObjectHandle

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
AREthGetProvidedObjectHandle cannot be called within `on prestart`.

## Function Syntax

```plaintext
dword AREthGetProvidedObjectHandle( char objectSymbolicQualifier[] );
```

## Description

Enables to search for a provided object which has been created separately.

## Parameters

- **objectSymbolicQualifier**: Symbolic qualifier identifying uniquely a FIBEX 4.1 database object. For syntax see [Symbolic Database Access SOME/IP](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPConfigFromDataBase.md).

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
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

  dword psi; // provided service instance handle
  dword peg; // provided event group handle
  dword pev; // provided event handle
  dword pfNotifier; // provided field notifier handle
  dword pfGetter; // provided field getter handle
  dword pfSetter; // provided field setter handle

  // Get handle of the provided service instance named "Service_Test"
  psi = AREthGetProvidedObjectHandle("Service_Test");

  // Get handle of the provided event group named "All"
  peg = AREthGetProvidedObjectHandle ("Service_Test::All");

  // Modify the unicast/multicast threshold that for one
  // subscriber the event and field notification are sent
  // per unicast
  AREthSetProperty(peg,"UnicastLimit", 1);

  // Get handle of the provided event "Event_Test"
  pev = AREthGetProvidedObjectHandle ("Event_Test");

  // Send the provided event "Event_Test" cyclically every 1 s
  AREthSetProperty(pev,"CycleTimeMs",1000);

  // Get handle of the provided field notification named "Field_Test"
  pfNotifier = AREthGetProvidedObjectHandle ("Field_Test");

  // Send the provided field notification named "Field_Test" cyclically every 2 s
  AREthSetProperty(pfNotifier,"CycleTimeMs",2000);

  // Get handle of the provided field getter named "Field_Test"
  pfGetter = AREthGetProvidedObjectHandle ("get_Field_Test");

  // Register a CAPL callback for this getter request
  AREthRegisterCallback(pfGetter, "OnAREthFieldGetterRequest");

  // Get handle of the provided field setter named "Field_Test"
  pfSetter = AREthGetProvidedObjectHandle ("set_Field_Test");

  // Register a CAPL callback for this setter request
  AREthRegisterCallback(pfSetter, "OnAREthFieldSetterRequest");
}

void OnAREthFieldGetterRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  write ("Field getter request received");
  // do something here
}

void OnAREthFieldSetterRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  write ("Field setter request received");
  // do something here
}
```

[See Also](javascript:void(0);)
