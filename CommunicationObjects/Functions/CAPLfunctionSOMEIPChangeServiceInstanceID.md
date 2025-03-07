[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSOMEIPChangeServiceInstanceID.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » SOMEIP_ChangeServiceInstanceID

# SOMEIP_ChangeServiceInstanceID (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
int SOMEIP_ChangeServiceInstanceID( serviceProviderRef* serviceProvider, dword instanceID ); // form 1
int SOMEIP_ChangeServiceInstanceID( serviceConsumerRef* serviceConsumer, dword instanceID ); // form 2
```

## Description

Changes the SOME/IP service instance ID of a provided service instance or the instance ID to which a consumed service should subscribe.

Before `SOMEIP_ChangeServiceInstanceID` is called, deactivate the simulated service instance first with `serviceProviderRef::ReleaseService`. Then change the service instance ID and restart the service again with `serviceProviderRef::ProvideService()`.

## Parameters

- **serviceProvider**: Service provider of which the service instance ID should be changed.
- **serviceConsumer**: Service consumer of which the service instance ID should be changed.
- **instanceID**: New service instance ID.

## Return Values

- **0**: Success
- **-1**: Service object is not initialized
- **-2**: Service object is not simulated
- **-3**: Invalid service object

## Example

```plaintext
// stop service instance
PSIEngine1.consumerSide[DRV,HPCM].ReleaseService();
PSIEngine1.providerSide[HPCM].ReleaseService();
// change service instance ID to 2
SOMEIP_ChangeServiceInstanceID( CommunicationObjects::PSIEngine1.providerSide[HPCM], 2 );

// restart service instance
PSIEngine1.providerSide[HPCM].ProvideService();
PSIEngine1.consumerSide[DRV,HPCM].RequestService();
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)