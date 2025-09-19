[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpSDServerEventGroupStatusChanged.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpSDServerEventGroupStatusChanged**

# OnSomeIpSDServerEventGroupStatusChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpSDServerEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status, dword newIpAddress, dword newPort ); // form 1
```

```plaintext
void OnSomeIpSDServerEventGroupStatusChanged( dword serviceId, dword majorVersion, dword instanceId, dword eventGroupId, long status, dword newIpAddress, dword newPort ); // form 2
```

## Description

This callback function can be implemented in the CAPL program if a Service Server wants to be notified whenever a Subscriber is added. This function is called when a Client executes a **subscribe eventgroup command**.

## Parameters

- **serviceId**: ID of the service whose status has changed.
- **instanceId**: Instance ID
- **eventGroupId**: ID of the Event Group.
- **status**:
  - 0: not subscribed
  - 1: subscribed
- **newIpAddress**: IPv4 address via which the subscription was received.
- **newPort**: Source port via which the subscription was received.
- **majorVersion**: Service interface major version.

## Return Values

—

## Example

```plaintext
void OnSomeIpSDServerEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status, dword newIpAddress, dword newPort)
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
