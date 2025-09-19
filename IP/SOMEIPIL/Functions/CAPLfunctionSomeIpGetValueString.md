[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetValueString.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetValueString**

# SomeIpGetValueString

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpGetValueString( dword objectHandle, char valuePath[], dword bufferLength, char buffer[] );
```

## Description

This function can be used to read out a string from the object specified in the **objectHandle** parameter. For Enum data types, the function returns the symbolic value.

**Note**

- At present, only the basic A_ASCIISTRING data type is supported.
- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a SOME/IP IL object, which must be completely described in the FIBEX database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

- **valuePath**: Path of the value to be read out. For specification of complex paths, a corresponding syntax must be adhered to.

- **bufferLength**: Length of the buffer parameter in bytes. If the selected buffer length is too small, the function copies only the number of characters (including null termination) that fit in the buffer.

- **buffer**: After execution, this parameter contains the null-terminated string. See [BOM in SOME/IP UTF8 and UTF16 strings](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPBOM.md).

## Return Values

- **Number of copied bytes**: In case of an error, the function returns 0, and the exact [error code](../../CAPLfunctionsSOMEIPILErrorCodes.md) can be queried with [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md). See [BOM in SOME/IP UTF8 and UTF16 strings](../../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPBOM.md).

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**.

```plaintext
variables
{
  DWORD gPm; // provided method handle
}

void Initialize()
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided Service Instance handle

  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  psi = SomeIpCreateProvidedServiceInstance(aep,11,1);

  // create method
  gPm = SomeIpAddMethod(psi,31,"OnMethodRequest");
}

void OnMethodRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  CHAR Member_value1[256];  // value of input parameter 1
  WORD val2;                // value of input parameter 2
  DWORD res;                // value of return parameter

  // get value from request
  SomeIpGetValueString(messageHandle,"Member_value1",elcount(Member_value1),Member_value1);
  val2 = (WORD)SomeIpGetValueDWord(messageHandle,"Member_value2");

  // do something here
}
```

[See Also](javascript:void(0);)
