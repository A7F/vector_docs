[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefIsConnected.md)

## distObjRef::IsConnected

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::IsConnected

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

- `dword distObjRef::IsConnected(); // form 1`
- `dword distObjMemberRef::IsConnected(); // form 2`

**Note**: Only available for consumed/provided members.

### Description

**Form1**: Checks if every member of the object is connected to its virtual network.

**Form2**: Checks if the object member is connected to its assigned virtual network.

### Parameters

—

### Return Values

- **Form1**: The value 1 is returned if all members are connected. Otherwise 0 is returned.
- **Form2**: The value 1 is returned if the member is connected. Otherwise 0 is returned.

### Example

**Example Form 1**

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  if (object.IsConnected())
  {
    write("Connected");
  }
}
```

**Example Form 2**

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  if (object.ExampleMember.IsConnected())
  {
    write("Connected");
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
