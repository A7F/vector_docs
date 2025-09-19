[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Proj/Functions/CAPLfunctionProjTransformToGeo.md)

[CAPL Functions](../../CAPLfunctions.md) » [Proj](../CAPLfunctionsProjOverview.md) » Proj_TransformToGeo

# Proj_TransformToGeo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long result;
result =  Proj_TransformToGeo(x, y, z, out latitude, out longitude, out elevation);
```

## Description

This function transforms an inertial coordinate to a geodetic coordinate. Proj_Create has to be called first to initialize the Proj Access with a definition/proj_string.

## Parameters

- **X**: Inertial X
- **Y**: Inertial Y
- **Z**: Inertial Z
- **Out Latitude**: Geodetic coordinate
- **Out Longitude**: Geodetic coordinate
- **Out Elevation**: Geodetic coordinate

## Return Values

- **long**: 0 if transformation is correct, `<> 0` otherwise

## Example

```plaintext
void proj_convert_to_geo()
{
  float i_x, i_y, i_z;
  float lat, lng, elev;

  i_x = -1436.30287110635;
  i_y = 1107.91554956408;
  i_z = 445.773842805044;

  if(Proj_Create("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs")==0)
  {
    Proj_TransformToGeo(i_x, i_y, i_z, lat, lng, elev);
    write("Result: Latitude: %f, Longtitude: %f, Elevantion: %f", lat, lng, elev);
  }
}
```

## Availability

- **Since Version**
  - CANoe: 17 SP2
  - vTESTstudio: 8

- **CANalyzer Measurement Setup (Transmit Branch)**
  - CANoe: N/A

- **CANoe Measurement Setup / CANalyzer Analysis Branch**
  - CANoe: —

- **CANoe Simulation Setup**
  - CANoe: ✔

- **CANoe Communication Setup**
  - CANoe: ✔

- **CANoe Test Setup for Test Modules**
  - CANoe: ✔

- **CANoe Test Setup for Test Units**
  - CANoe: ✔

- **32-Bit**
  - CANoe: ✔

- **64-Bit**
  - CANoe: ✔

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)