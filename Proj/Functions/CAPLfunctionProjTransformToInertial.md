[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Proj/Functions/CAPLfunctionProjTransformToInertial.md)

## CAPL Functions » Proj » Proj_TransformToInertial

### Proj_TransformToInertial

**Valid for:** CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
long result;
result = Proj_TransformToInertial(latitude, longitude, elevation, out x, out y, out z);
```

### Description

This function transforms an inertial coordinate to a geodetic coordinate. Proj_Create has to be called first to initialize the Proj Access with a definition/proj_string.

### Parameters

- **Latitude**: Geodetic coordinate
- **Longitude**: Geodetic coordinate
- **Elevation**: Geodetic coordinate
- **Out X**: Inertial X
- **Out Y**: Inertial Y
- **Out Z**: Inertial Z

### Return Values

- **long**: 0 if transformation is correct, `<> 0` otherwise

### Example

```c
void proj_convert_to_inertial() {
  float lat, lng, elev;
  float i_x, i_y, i_z;

  lat = 8.87994143680241;
  lng  = 48.7307623275145;
  elev = 445.773842805044;

  if(Proj_Create("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs")==0) {
    Proj_TransformToInertial(lat, lng, elev, i_x, i_y, i_z);
    write("Result: x: %f, y: %f, z: %f", i_x, i_y, i_z);
  }
}
```

### Availability

- **Since Version**: 
  - CANoe: 17 SP2
  - vTESTstudio: 8
- **Restricted To**: N/A
- **CANalyzer Measurement Setup (Transmit Branch)**: N/A
- **CANoe Measurement Setup / CANalyzer Analysis Branch**: N/A
- **CANoe Simulation Setup**: ✔
- **CANoe Communication Setup**: ✔
- **CANoe Test Setup for Test Modules**: ✔
- **CANoe Test Setup for Test Units**: ✔
- **32-Bit**: ✔
- **64-Bit**: ✔

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)