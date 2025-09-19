[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetConsumedObjectHandle.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthGetConsumedObjectHandle

# AREthGetConsumedObjectHandle

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
AREthGetConsumedObjectHandle cannot be called within `on prestart`.

## Function Syntax

```plaintext
dword AREthGetConsumedObjectHandle( char objectSymbolicQualifier[] );
```

## Description

Enables to search for a consumed object which has been created separately.

## Parameters

- **objectSymbolicQualifier**: Symbolic qualifier identifying uniquely a FIBEX 4.1 database object. For syntax see [Symbolic Database Access SOME/IP](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPConfigFromDataBase.md).

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the looked for object.

## Example

```plaintext
variables
{
  dword gCev; // consumed event handle
  dword gCfNotifier; // consumed field notifier handle
  dword gCfGetter; // consumed field getter handle
  dword gCfSetter; // consumed field setter handle
  msTimer gTimer;
}

on start
{
  // That the following code works there must be in the FIBEX 4.1
  // database a node consuming under an unreliable endpoint
  // (UDP socket) the following objects:
  //  - A service instance named "Service_Test"
  //  - An event group named "All" belonging to "Service_Test"
  //  - An event named "Event_Test" belonging to "All"
  //  - A field named "Field_Test" belonging to "All" and having a notifier, a getter and a setter
  //  - A node providing the event group "All"

  // Get handle of the consumed event named "Event_Test"
  gCev = AREthGetConsumedObjectHandle ("Service_Test::Event_Test");

  // Register a CAPL callback for this event notification
  AREthRegisterCallback(gCev, "OnAREthEventReceived");

  // Get handle of the consumed field notification named "Field_Test"
  gCfNotifier = AREthGetConsumedObjectHandle ("Field_Test");

  // Register a CAPL callback for this field notification
  AREthRegisterCallback(gCfNotifier, "OnAREthFieldNotificationReceived");

  // Get handle of the consumed field getter named "Field_Test"
  gCfGetter = AREthGetConsumedObjectHandle ("get_Field_Test");

  // Register a CAPL callback for this getter response
  AREthRegisterCallback(gCfGetter, "OnAREthFieldGetterResponse");

  // Get handle of the consumed field setter named "Field_Test"
  gCfSetter = AREthGetConsumedObjectHandle ("set_Field_Test");

  // Register a CAPL callback for this setter response
  AREthRegisterCallback(gCfSetter, "OnAREthFieldSetterResponse");

  // Start timer
  setTimer(gTimer, 3000);
}

on timer gTimer
{
  // Call the field setter and getter
  AREthCallMethod(gCfGetter);
  AREthCallMethod(gCfSetter);
  // Restart timer
  setTimer(gTimer, 3000);
}

void OnAREthEventReceived( dword cevHandle, dword messageHandle )
{
  write ("Event notification received");
  // do something here
}

void OnAREthFieldNotificationReceived( dword cfHandle, dword messageHandle )
{
  write ("Field notification received");
  // do something here
}

void OnAREthFieldGetterResponse(dword methodCallHandle, dword messageResponseHandle )
{
  write ("Field getter response received");
  // do something here
}

void OnAREthFieldSetterResponse(dword methodCallHandle, dword messageResponseHandle )
{
  write ("Field setter response received");
  // do something here
}
```

[See Also](javascript:void(0);)
- AREthGetConsumedObjectHandle
- [AREthGetProvidedObjectHandle](CAPLfunctionAREthGetProvidedObjectHandle.md#aanchor17612)
- [AREthRegisterCallback](CAPLfunctionAREthRegisterCallback.md#aanchor7810)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
