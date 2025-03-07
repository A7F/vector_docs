[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalStopControlSimulationNode.md)

## SecurityLocalStopControlSimulationNode

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalStopControlSimulationNode

**Valid for:** [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

### Function Syntax

- `long SecurityLocalStopControlSimulationNode(char nodeName[], char networkName[])` // form 1
- `long SecurityLocalStopControlSimulationNode(char nodeId[], dword nodeIdType, char networkName[])` // form 2

### Description

Stops controlling (deregistration) the specified simulation node on the specified network.

After a successful deregistration, you cannot call any `SecurityOfNode…()` functions at the previously registered node, neither will you receive any `OnSecurityOfNode…` callbacks.

You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) to register.

### Parameters

- **char nodeName[]**: The name of the node to deregister from. This refers to the name declared in the database. (Form 1)
- **char nodeId[]**: The name or title of the node to deregister from. Use either the node name of a network node declared in the database or the node title declared in the Simulation Setup of the CANoe DE product and set parameter nodeIdType accordingly. (Form 2)
- **dword nodeIdType**: Configure how the parameter nodeId shall be interpreted.
  - Possible Values:
    - 1: nodeId refers to node name of a network node declared in the database
    - 2: nodeId refers to node title declared in the Simulation Setup of the CANoe DE product
- **char networkName[]**: The name of the network the node to deregister from is on.

### Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error. A value larger than 1 means warning.

- **1**: Success.
- **0**: Error, no details.
- **-1**: Error - Specified Node unknown.
- **-2**: Error - Specified Node unknown at the specified network.
- **-3**: Error - StartControl failed.
- **-4**: Error - Not registered at any node.
- **-5**: Error - Not registered at specific node.
- **2**: Warning - Not registered at any node.
- **3**: Warning - Not registered at specific node.

### Example

```plaintext
//form 1
on start
{
  dword result = 0;
  result = SecurityLocalStartControlSimulationNode("DatabaseNode", "CAN", 2);
  Write("SecurityLocalStartControlSimulationNode for network node with name DatabaseNode returned %i", result);
}

on stopMeasurement
{
  dword result = 0;
  result = SecurityLocalStopControlSimulationNode("DatabaseNode", "CAN");
  Write("SecurityLocalStopControlSimulationNode for network node with name DatabaseNode returned %i", result);
}

//form 2
on start
{
  dword result = 0;
  result = SecurityLocalStartControlSimulationNode("MyNode", 2, "CAN", 2); //Use the node title, if the node is not declared in the database (Network Node is set to <<default>>)
  Write("SecurityLocalStartControlSimulationNode for node with title MyNode returned %i", result);
}

on stopMeasurement
{
  dword result = 0;
  result = SecurityLocalStopControlSimulationNode("MyNode", 2, "CAN"); //Use the node title, if the node is not declared in the database (Network Node is set to <<default>>)
  Write("SecurityLocalStopControlSimulationNode for node with title MyNode returned %i", result);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)