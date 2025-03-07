[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **Syntax for Predefined Service Discovery (SD) Access Paths**

# Syntax for Predefined Service Discovery (SD) Access Paths

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Examples

- **Flags**
  - `AREthSetValueDWord(msg, "Flags", 0xC0); //set reboot (0x80) and unicast (0x40) flag`
- **Reserved**
  - `AREthSetValueDWord(msg, "Reserved", 0x00);`

### Entry[n]

- **FindService, OfferService, RequestService, RequestServiceAck**
  - **Index1stOptions**
  - **Index2ndOptions**
  - **NumberOfOptions1**
  - **NumberOfOptions2**
  - **ServiceID**
  - **InstanceID**
  - **MajorVersion**
  - **TTL**
  - **MinorVersion**
  - Example: `AREthSetValueDWord(msg, "Entry[9].FindService.ServiceID", 0x000A);`

- **FindEventgroup, Publish, Subscribe, SubscribeAck**
  - **Index1stOptions**
  - **Index2ndOptions**
  - **NumberOfOptions1**
  - **NumberOfOptions2**
  - **ServiceID**
  - **InstanceID**
  - **MajorVersion**
  - **TTL**
  - **Reserved**
  - **EventgroupID**
  - Example: `dword evgID = AREthGetValueDWord(msg, "Entry[0].SubscribeAck.EventgroupID");`

### Option[n]

- **Configuration**
  - **Reserved**
  - **String[n]**
  - Example: `AREthSetValueString(msg, "Option[2].Configuration.String[1]", "def=123");`

- **LoadBalancing**
  - **Reserved**
  - **Priority**
  - **Weight**
  - Example: `dword prio = AREthGetValueDWord(msg, "Option[5].LoadBalancing.Priority");`

- **Protection**
  - **Reserved**
  - **ID**
  - **AliveCounter**
  - **CRC**
  - Example: `dword res = AREthGetValueDWord(msg, "Option[0].Protection.Reserved");`

- **IPv4Endpoint**
  - **Reserved**
  - **IPv4Address**
  - **Reserved_2**
  - **L4Proto**
  - **PortNumber**
  - Example: `AREthSetValueDWord(msg, "Option[0].IPv4Endpoint.PortNumber", 30490);`

- **IPv6Endpoint**
  - **Reserved**
  - **IPv6Address[16]**
  - **Reserved_2**
  - **L4Proto**
  - **PortNumber**
  - Example: `dword prot = AREthGetValueDWord(msg, "Option[4].IPv6Endpoint.L4Proto");`

- **IPv4Multicast**
  - **Reserved**
  - **IPv4Address**
  - **Reserved_2**
  - **L4Proto**
  - **PortNumber**
  - Example: `AREthSetValueDWord(msg, "Option[0].IPv4Multicast.PortNumber", 30490);`

- **IPv6Multicast**
  - **Reserved**
  - **IPv6Address[16]**
  - **Reserved_2**
  - **L4Proto**
  - **PortNumber**
  - Example: `AREthSetValueDWord(msg, "Option[6].IPv6Multicast.IPv6Address[9]", 0xFE);`

### Example

```c
void OnAREthMessage( dword messageHandle )
{
  DWORD nbrOfEntries;
  BYTE i;
  CHAR valuePath[255];
  DWORD entryType;
  DWORD nbrOfOptions;
  DWORD optionType;

  if(AREthGetMessageId(messageHandle) == 0xFFFF8100)
  {
    nbrOfEntries = AREthGetValueDWord(messageHandle, "Entry");

    for(i=0; i<nbrOfEntries; i++)
    {
      snprintf(valuePath, elCount(valuePath), "Entry[%d]", i);
      entryType = AREthGetValueDWord(messageHandle, valuePath);

      switch(entryType)
      {
        case 0x00 /*FindService*/:
          snprintf(valuePath, elCount(valuePath), "Entry[%d].FindService.ServiceID", i);
          write("FindService with ServiceID %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x01 /*OfferService*/:
          snprintf(valuePath, elCount(valuePath), "Entry[%d].OfferService.ServiceID", i);
          write("OfferService with ServiceID %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x06 /*Subscribe*/:
          snprintf(valuePath, elCount(valuePath), "Entry[%d].Subscribe.EventgroupID", i);
          write("Subscribe with EventgroupID %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x07 /*SubscribeAck*/:
          snprintf(valuePath, elCount(valuePath), "Entry[%d].SubscribeAck.EventgroupID", i);
          write("SubscribeAck with EventgroupID %d", AREthGetValueDWord(messageHandle, valuePath));
          break;
      }
    }

    nbrOfOptions = AREthGetValueDWord(messageHandle, "Option");

    for(i=0; i<nbrOfOptions; i++)
    {
      snprintf(valuePath, elCount(valuePath), "Option[%d]", i);
      optionType = AREthGetValueDWord(messageHandle, valuePath);

      switch(optionType)
      {
        case 0x01 /*Configuration*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].Configuration.String[1]", i);
          write("Configuration with String[1] %s", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x02 /*LoadBalancing*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].LoadBalancing.Priority", i);
          write("LoadBalancing with Priority %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x03 /*Protection*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].Protection.ID", i);
          write("Protection with ID %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x04 /*IPv4Endpoint*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].IPv4Endpoint.PortNumber", i);
          write("IPv4Endpoint with PortNumber %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x06 /*IPv6Endpoint*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].IPv6Endpoint.PortNumber", i);
          write("IPv6Endpoint with PortNumber %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x14 /*IPv4Multicast*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].IPv4Multicast.PortNumber", i);
          write("IPv4Multicast with PortNumber %d", AREthGetValueDWord(messageHandle, valuePath));
          break;

        case 0x16 /*IPv6Multicast*/:
          snprintf(valuePath, elCount(valuePath), "Option[%d].IPv6Multicast.PortNumber", i);
          write("IPv6Multicast with PortNumber %d", AREthGetValueDWord(messageHandle, valuePath));
          break;
      }
    }
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)