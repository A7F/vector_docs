# _DoIP_VehicleAnnouncementInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void _DoIP_VehicleAnnouncementInd(char VIN[], WORD logAddr, BYTE entityIdent[], BYTE groupIdent[], BYTE furtherActionRequired, BYTE VINGIDsyncStatus)
```

## Description

A Vehicle Announcement Message (VAM) has been received, possibly as a Vehicle Identification Response for a Vehicle Identification Request (VIR) Message. The responding vehicle indicates its presence.

If the responding vehicle’s VIN or EID has been selected as VIR parameter, this vehicle will be selected for communication.

## Parameters

- **VIN**: Vehicle Identification Number (typically 17 characters). It is possible that a responding vehicle does not have a VIN yet.
- **logAddr**: Logical DoIP address of the responding entity, e.g. the gateway.
- **entityIdent**: (6 byte) Entity ID of the vehicle, often the Ethernet MAC address of the network interface controller transmitting the response.
- **groupIdent**: (6 byte) Group ID of the vehicle.
- **furtherActionRequired**: Indicates if a special routing activation method is required.
- **VINGIDsyncStatus**: Indicates if the VIN and GID are already synchronized (0x0) or not (0x10).

## Return Values

—

## Example

```plaintext
void _DoIP_VehicleAnnouncementInd( char VIN[], WORD logAddr, BYTE entityIdent[], BYTE groupIdent[], BYTE furtherActionReq, BYTE VINGIDsyncStatus)
{
  WORD i;
  write( "[%.3f] Vehicle Announcement Message from '%s'", timenow()/100000.0, VIN);

  // Store the VIN of the responding vehicle in a table,
  // if it is not known already

  for( i = 0; i < gVehiclesFound; ++i)
  {
    if( 0 == strncmp( VIN, gVehicleAnswered[i], elcount(VIN)))
    return; // vehicle already registered, so do not store it again
  }

  if( gVehiclesFound < elcount( gVehicleAnswered))
  {
    strncpy( gVehicleAnswered[ gVehiclesFound], VIN, elcount( gVehicleAnswered[ gVehiclesFound]));
    ++gVehiclesFound;
  }
}
```
