[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpSDClientServiceStatusChanged.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpSDClientServiceStatusChanged**

# OnSomeIpSDClientServiceStatusChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpSDClientServiceStatusChanged( dword serviceId, dword instanceId, LONG  status ); // form 1
void OnSomeIpSDClientServiceStatusChanged( dword serviceId, dword majorVersion, dword instanceId, LONG status ); // form 2
```

## Description

This callback function can be implemented in the CAPL program, if the Client wants to be notified of status changes to the services. The function is called when the status of a service changes. The callback is called regardless of whether or not the service is consumed by [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md).

## Parameters

- **serviceId**: ID of the service whose status has changed.
- **instanceId**: Instance ID
- **status**:
  - 0: down
  - 1: up
- **majorVersion**: Service interface major version.

## Return Values

—

## Example

```plaintext
void OnSomeIpSDClientServiceStatusChanged( dword serviceId, dword majorVersion, dword instanceId, LONG status)
{
  char buffer[100];
  if(status == 0)
  {
    snprintf(buffer,elcount(buffer),"Service down");
  }
  else if(status == 1)
  {
    snprintf(buffer,elcount(buffer),"Service up");
  }
  else
  {
    snprintf(buffer,elcount(buffer),"Undefined status");
  }
  write("Service %d (instance %d, major version %d): %s",serviceId,instanceId,majorVersion,buffer);
}
```

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
