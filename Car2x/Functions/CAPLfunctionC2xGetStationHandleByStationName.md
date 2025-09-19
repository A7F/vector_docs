[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationHandleByStationName.md)

## C2xGetStationHandleByStationName

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xGetStationHandle

**Valid for**: CANoe DE

### Function Syntax

```plaintext
long C2xGetStationHandle(long packetHandle);
long C2xGetStationHandle(char *dbNodeName);
```

### Description

Retrieves an ITS station handle by the name of the ITS station. The handle can be used as input for the other functions of the Station API, for instance [C2xAssignNodeToStation](CAPLfunctionC2xAssignNodeToStation.md).

### Parameters

- **stationName**: Name of the station as displayed in the ITS Station Manager.

### Return Values

- **0**: Station handle for parameter stationName not available
- **≠0**: Station handle

### Example

```plaintext
on key 'a'
{
    long stationHdl;

    stationHdl = C2xGetStationHandleByStationName("Car1");
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
