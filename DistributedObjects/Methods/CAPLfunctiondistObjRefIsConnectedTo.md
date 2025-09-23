[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefIsConnectedTo.md)

## distObjRef::IsConnectedTo

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::IsConnectedTo

### Method Syntax

dword [distObjRef](../Objects/CAPLfunctiondistObjRef.md)::IsConnectedTo(virtNet network);

### Description

Checks if every member of the object is connected, if it is assigned to the given virtual network.

### Parameters

- **network**: Virtual network to check.

### Return Values

The value 1 is returned if all members are connected. Otherwise 0 is returned.

### Example

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  if (object.IsConnectedTo(virtNet::Default))
  {
    write("Connected");
  }
}
```
