[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnSOMEIPEventGroupSubscribedConsumerSide.md)

**CAPL Functions** » **Communication Objects** » **on SOMEIP_EventGroupSubscribedConsumerSide**

# on SOMEIP_EventGroupSubscribedConsumerSide (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`on SOMEIP_EventGroupSubscribedConsumerSide <EventGroup>;`

## Description

The event procedure is called at the consumer when an event group subscription has been accepted by the provider and SOME/IP binding is used.

## Parameters

- **<EventGroup>**: Designates the event group on which the event procedure shall react. This must be a consumer endpoint.

## Selectors

- **Selector**: provider
  - **Description**: Provider
  - **Type**: The type is serviceProviderRef*
  - **Access Limitation**: Read only

- **Selector**: Status
  - **Description**: Int, 1 means connected, 2 means not connected.
  - **Type**: Uint32
  - **Access Limitation**: Read only

## Example

```plaintext
on SOMEIP_EventGroupSubscribedConsumerSide <EventGroup>
{
  if (this.Status == 1) // Positive Acknowledgement
  {
    ...
  }
  else if (this.Status == 0) // Negative Acknowledgement
  {
    write("%s", this.provider.Name);
  }
}
```

[on SOMEIP_EventGroupSubscribed](CAPLfunctionOnSOMEIPEventGroupSubscribed.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)