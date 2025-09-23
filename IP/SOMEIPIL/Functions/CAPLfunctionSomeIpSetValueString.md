# SomeIpSetValueString

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long SomeIpSetValueString( dword objectHandle, char valuePath[], char value[] ); // form 1`
- `long SomeIpSetValueString( dword objectHandle, char valuePath[], char value[], long valueLength); // form 2`

## Description

This function can be used to set a string in the object specified in the **objectHandle** parameter. Enum data types can be set with one of their symbolic values using this function.

**Note:**

- At present, only the basic A_ASCIISTRING data type is supported.
- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a SOME/IP IL object, which must be completely described in the FIBEX database. Supported objects:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

- **valuePath**: Path of the value to be set. For specification of complex paths, a corresponding syntax must be adhered to.

- **value**: New value (this string must be specified as null-terminated string). See [BOM in SOME/IP UTF8 and UTF16 strings](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPBOM.md).

- **valueLength**: Length of the input string in characters.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

In this example, it is assumed that a service with **ID 10** (instance ID 1) is contained in the FIBEX database that is assigned to the CANoe configuration. The service provides an Event that transfers in the structured parameter **param 1** the date **Error_Message**.

```plaintext
void Initialize()
{
  DWORD aep; // application endpoint handle
  DWORD psi; // provided service handle
  DWORD peg; // provided eventgroup handle
  DWORD pev; // provided event handle

  // open application endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create service instance
  psi = SomeIpCreateProvidedServiceInstance(aep,10,1);

  // create eventgroup
  peg = SomeIpAddProvidedEventGroup(psi,1);

  // create event and add event to eventgroup
  pev = SomeIpAddEvent(psi, 1, "OnPrepareEvent1");
  SomeIpAddEventToEventgroup(peg, pev);

  // ensure that event is sent cyclically
  SomeIpSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the event is sent. Parameters can be specified here.

  // set parameter "Error_Message" of struct "param1"
  SomeIpSetValueString(messageHandle,"param1.Error_Message","Error Text");
}
```

[See Also](javascript:void(0);)
