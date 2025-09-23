# AREthSDSetServiceStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSDSetServiceStatus( dword psiHandle, long up );
```

## Description

The status of the Provided Service Instance is set at the node (producer).

## Parameters

- **psiHandle**: Handle of the required Consumed Service Instance (see [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md)).
- **up**:
  - 1: The status is changed to **up**. The sending of OfferServices is started.
  - 0: The status is changed to **down**. A StopOfferService message is sent if the service was previously in **up** status.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
dword appEndpointHandle;
dword serviceHandle;

appEndpointHandle = AREthOpenLocalApplicationEndpoint(kUDP, 30501);
serviceHandle  = AREthCreateConsumedServiceInstance(appEndpointHandle, 1 /*serviceId*/, 1 /*instanceId*/);
AREthSDSetServiceStatus(serviceHandle, 0); //do not offer this service
```

[See Also](javascript:void(0);)
