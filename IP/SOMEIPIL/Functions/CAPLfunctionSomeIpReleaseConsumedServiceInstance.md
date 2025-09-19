[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpReleaseConsumedServiceInstance.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpReleaseConsumedServiceInstance**

# SomeIpReleaseConsumedServiceInstance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG SomeIpReleaseConsumedServiceInstance(dword csiHandle );
```

## Description

Deletes a Consumed Service Instance that was created by [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md).

The objects assigned to the Service Instance (Eventgroups, Events, fields, and methods) are deleted when the Service Instance is closed. If the Service Instance is newly created, all objects must also be newly created.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance to be deleted.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 'c'
{
  DWORD aep; // Application Endpoint handle
  DWORD csi; // consumed Service Instance handle

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,10,1);

  // ... do something here

  // release the consumed Service Instance
  SomeIpReleaseConsumedServiceInstance(csi);

  // ... Application Endpoint can still be used here
}
```

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
