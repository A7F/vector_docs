[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xApplyPathHistory.md)

**CAPL Functions** » **Car2x** » **C2xApplyPathHistory**

# C2xApplyPathHistory

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xApplyPathHistory(long packet, double latitude, double longitude, double maxDistance)` // form 1
- `long C2xApplyPathHistory(long packet, double latitude, double longitude, double elevation, double maxDistance, long maxPtCount, long routeId)` // form 2

## Description

This function applies values to multiple path history tokens in the packet. The geographical route of the station (path of the movement) is taken from the scenario route of the station or, when no scenario is applied to this station, from previous calls of the C2xAddGeoPos function. This function applies the path history data to the following packet and tokens:

- CAM (ETSI), tokens: `cam.camParameters.lowFrequencyContainer.basicVehicleContainerLowFrequency.pathHistory.[i].pathPosition`
- DENM (ETSI), tokens: `denm.location.traces.[0].[i].pathPosition`
- BasicSafetyMessage (US SAE), tokens: `value.basicSafetyMessage.partII.[0].partII_Value.vehicleSafetyExt.pathHistory.crumbData.[i]`
- BasicSafetyMessage (China CSAE), tokens: `bsmFrame.safetyExt.pathHistory.crumbData.[i].llvOffset.offsetLL.position_LatLon`

## Parameters

- **packet**: Handle of a packet that has been created with C2xInitPacket or was provided as callback function parameter.
- **latitude**: New station latitude in degrees, -90.0° < latitude < 90.0°.
- **longitude**: New station longitude in degrees, -180.0° <= longitude <= 180.0°.
- **elevation (optional)**: New station altitude in meters, -1000.0m <= elevation <= 8000.0m. Set the elevation parameter to a value outside of the valid range to indicate that the elevation is not provided / is unused.
- **maxDistance**: Maximal length in meters of the path history. 0.0m < maxDistance < 1000.0m. Set values below 1000 (m) to limit the geographical length of the station path history applied by this function.
- **maxPtCount**: Maximal count of path history points applied by this function. It is limited by the allowed maximal length of path history sequence token in the database for concrete packet (CAM, DENM, BasicSafetyMessage).
- **routeId**: Unique integer number which identifies the path history data storage from where the position data will be used. The path history data source here are previous periodic calls to the CAPL Function C2xAddGeoPos with the same value of routeId parameter. Valid value range: routeId > 0.

## Return Values

- **0**: No error, OK
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```c
void OnPreTxCAM(LONG packet)
{
  C2xApplyPathHistory(packet, @GPS::GPS1.Latitude, @GPS::GPS1.Longitude, @GPS::GPS1.Altitude, 1000);
  C2xCompletePacket(packet);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)