[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSDSetServiceStatus.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpSDSetServiceStatus**

# SomeIpSDSetServiceStatus

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSDSetServiceStatus( dword psiHandle, long up );
```

## Description

The status of the Provided Service Instance is set at the node (producer).

## Parameters

- **psiHandle**: Handle of the required Consumed Service Instance (see [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md)).
- **up**:
  - 1: The status is changed to **up**. The sending of OfferServices is started.
  - 0: The status is changed to **down**. A StopOfferService message is sent if the service was previously in **up** status.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
dword appEndpointHandle;
dword serviceHandle;

appEndpointHandle = SomeIpOpenLocalApplicationEndpoint(kUDP, 30501);
serviceHandle  = SomeIpCreateConsumedServiceInstance(appEndpointHandle, 1 /*serviceId*/, 1 /*instanceId*/);
SomeIpSDSetServiceStatus(serviceHandle, 0); //do not offer this service
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)