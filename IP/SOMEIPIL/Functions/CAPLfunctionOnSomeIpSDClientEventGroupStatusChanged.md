[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpSDClientEventGroupStatusChanged.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpSDClientEventGroupStatusChanged**

# OnSomeIpSDClientEventGroupStatusChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpSDClientEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status ); // form 1
void OnSomeIpSDClientEventGroupStatusChanged( dword serviceId, dword majorVersion, dword instanceId, dword eventGroupId, long status ); // form 2
```

## Description

This callback function can be implemented in the CAPL program if an Event Consumer (Client) wants to be notified of status changes to Event Groups. The function is called whenever the status of an Event Group changes. The callback function can only be called for status changes related to an Event Group that is consumed by this node.

## Parameters

- **serviceId**: ID of the service whose status has changed.
- **instanceId**: Instance ID
- **eventGroupId**: ID of the Event Group
- **status**:
  - 0: not subscribed
  - 1: subscribed
- **majorVersion**: Service interface major version.

## Return Values

—

## Example

```c
void OnSomeIpSDClientEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status)
{
  char buffer[100];
  if(status == 0)
  {
    snprintf(buffer,elcount(buffer),"not subscribed");
  }
  else if(status == 1)
  {
    snprintf(buffer,elcount(buffer),"subscribed");
  }
  else
  {
    snprintf(buffer,elcount(buffer),"Undefined status");
  }
  write("Event group (ID %d), of service %d (instance %d): %s",eventGroupId,serviceId,instanceId,buffer);
}
```

[See Also](javascript:void(0);)
```markdown