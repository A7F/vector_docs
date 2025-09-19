[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthRemoveMethod.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthRemoveMethod**

# AREthRemoveMethod

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveMethod( dword methodHandle );
```

## Description

This function removes a method from a Provided Service Instance.

Afterwards, the callback registered with [AREthAddMethod](CAPLfunctionAREthAddMethod.md) is no longer called.

## Parameters

- **methodHandle**: Handle of the method (see [AREthAddMethod](CAPLfunctionAREthAddMethod.md))

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**.

```plaintext
variables
{
  dword gPm; // provided method handle
}

void Initialize()
{
  dword aep; // Application Endpoint handle
  dword psi; // provided Service Instance handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,11,1);

  // create method
  gPm = AREthAddMethod(psi,31,"OnMethodRequest");
}

on key 'r'
{
  // remove method
  AREthRemoveMethod(gPm);
}
```

[See Also](javascript:void(0);)
