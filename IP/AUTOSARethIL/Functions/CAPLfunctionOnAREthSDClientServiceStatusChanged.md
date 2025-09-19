[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthSDClientServiceStatusChanged.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » OnAREthSDClientServiceStatusChanged

# OnAREthSDClientServiceStatusChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAREthSDClientServiceStatusChanged( dword serviceId, dword instanceId, LONG  status );
```

## Description

This callback function can be implemented in the CAPL program, if the Client wants to be notified of status changes to the services. The function is called when the status of a service changes. The callback is called regardless of whether or not the service is consumed by [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).

## Parameters

- **serviceId**: ID of the service whose status has changed.
- **instanceId**: Instance ID
- **status**:
  - 0: down
  - 1: up

## Return Values

—

## Example

```plaintext
void OnAREthSDClientServiceStatusChanged( dword serviceId, dword majorVersion, dword instanceId, LONG status)
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
