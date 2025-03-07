[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionGetHostVehicle.md)

**CAPL Functions** » **ADAS** » **GetHostVehicle**

# GetHostVehicle

**Valid for**: CANoe DE

**Note**  
This CAPL function is also available as C# function.

## Function Syntax

**C#**  
`GroundTruthAccess.GetHostVehicle.Call();`

**CAPL**  
`GroundTruthAccess.GetHostVehicle.Call();`

## Description

Gets the name of the host vehicle for the current ground truth. This host vehicle must be a moving object and defines a kind of center for the ground truth.

## Parameters

—

## Return Values

Name of host vehicle as string.

## Example

### CAPL

```plaintext
variables
{
  distObjRef ::_ADAS::DataModel::IMovingObject hostVehicle;
  char hostVehicleNameWithAdasPrefix [100];
}

on start
{
  snprintf(hostVehicleNameWithAdasPrefix, elcount(hostVehicleNameWithAdasPrefix),"ADAS::%s", GroundTruthAccess.GetHostVehicle.Call());
  hostVehicle = (distObjRef _ADAS::DataModel::IMovingObject) lookupDistObj(hostVehicleNameWithAdasPrefix);

  if(hostVehicle.IsValid)
  {
    // Access the host vehicle values, e.g:
    // $hostVehicle.moving_object.baseInfo.position.x.phys
  }
}
```

### C#

```plaintext
_ADAS.DataModel.IMovingObject GetHostVehicleObject()
{
  string gtHostVehicle = GroundTruthAccess.GetHostVehicle.Call();

  return DORegistry.LookupDistributedObject<_ADAS.DataModel.IMovingObject>(gtHostVehicle, "ADAS");
}

[OnKey('a')]
public void ShowHostVehicle(char c)
{
  var hostVehicle = GetHostVehicleObject();

  Output.WriteLine("Host vehicle: " + hostVehicle.Name);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)