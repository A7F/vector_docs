[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetValueString.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthSetValueString**

# AREthSetValueString

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSetValueString( dword objectHandle, char valuePath[], char value[] ); // form 1
long AREthSetValueString( dword objectHandle, char valuePath[], char value[], long valueLength); // form 2
```

## Description

This function can be used to set a string in the object specified in the **objectHandle** parameter. Enum data types can be set with one of their symbolic values using this function.

**Note**

- At present, only the basic A_ASCIISTRING data type is supported.
- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL object, which must be completely described in the AUTOSAR database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Path of the value to be set. For specification of complex paths, a corresponding syntax must be adhered to.

- **value**: New value (this string must be specified as null-terminated string). See [BOM in SOME/IP UTF8 and UTF16 strings](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPBOM.md).

- **valueLength**: Length of the input string in characters.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

In this example, it is assumed that a service with **ID 10** (instance ID 1) is contained in the FIBEX database that is assigned to the CANoe configuration. The service provides an Event that transfers in the structured parameter **param 1** the date **Error_Message**.

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
  // this function is called before the event is sent. Parameters can be specified here.

  // set parameter "Error_Message" of struct "param1"
  AREthSetValueString(messageHandle,"param1.Error_Message","Error Text");
}
```

[See Also](javascript:void(0);)