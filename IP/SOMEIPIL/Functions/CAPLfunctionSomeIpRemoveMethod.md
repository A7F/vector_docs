# SomeIpRemoveMethod

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpRemoveMethod( dword methodHandle );
```

## Description

This function removes a method from a Provided Service Instance. Afterwards, the callback registered with [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md) is no longer called.

## Parameters

- **methodHandle**: Handle of the method (see [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md))

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

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

on key 'r'
{
  // remove method
  SomeIpRemoveMethod(gPm);
}
```

[See Also](javascript:void(0);)
