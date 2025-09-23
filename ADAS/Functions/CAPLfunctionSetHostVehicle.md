[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionSetHostVehicle.md)

## SetHostVehicle

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » SetHostVehicle

**Valid for**: CANoe DE

**Note**  
This CAPL function is also available as C# function.

### Function Syntax

**C#**  
`GroundTruthAccess.SetHostVehicle.Call(42);`

**CAPL**  
`GroundTruthAccess.SetHostVehicle.Call(42);`

### Description

Sets the host vehicle for the current ground truth. This host vehicle must be a moving object and defines a kind of center for the ground truth (see example). For ground truth objects to be displayed in the Scene window, a host vehicle must be available.

### Parameters

- **HostVehicle Id**: Id of the host vehicle (moving object)

### Return Values

—

### Example

#### CAPL

```plaintext
GroundTruthAccess.SetHostVehicle.Call(42));
```

#### C#

```plaintext
GroundTruthAccess.SetHostVehicle.Call(42));
```
