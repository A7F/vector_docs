[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalStartControlSimulationNode.md)

### SecurityLocalStartControlSimulationNode

**CAPL Functions** » **Security** » SecurityLocalStartControlSimulationNode

**Valid for**: CANoe DE • CANoe4SW DE

#### Function Syntax

- `long SecurityLocalStartControlSimulationNode(char nodeName[], char networkName[], dword orderNumber)` // form 1
- `long SecurityLocalStartControlSimulationNode(char nodeId[], dword nodeIdType, char networkName[], dword orderNumber)` // form 2

#### Description

Registers the calling node to a node in the Simulation Setup. Both nodes require the **SecMgrCANoeClient** Nodelayer.

After a successful registration, the calling node can use all `SecurityOfNode…()` Functions to control the simulation node.

The calling node receives all `OnSecurityOfNode…` callbacks from the specified node on the specified network.

You have to call [SecurityLocalStopControlSimulationNode](CAPLfunctionSecurityLocalStopControlSimulationNode.md) to unregister.

Form 2 allows to control non-database simulation nodes.

#### Parameters

- **char nodeName[]**: The name of the node to control. This refers to the name declared in the database. (Form 1)
- **char nodeId[]**: The name or title of the node to control. Use either the node name of a network node declared in the database or the node title declared in the Simulation Setup of the CANoe DE product and set parameter nodeIdType accordingly. (Form 2)
- **dword nodeIdType**: Configure how the parameter nodeId shall be interpreted. Possible Values:
  - 1: nodeId refers to node name of a network node declared in the database
  - 2: nodeId refers to node title declared in the Simulation Setup of the CANoe DE product (If Network Node is set to `<``<default>``>`) (Form 2)
- **char networkName[]**: The name of the network the node to control is on.
- **dword orderNumber**: Defines the position in the ordered list, in which the callbacks are executed. Order number 1 is reserved for the simulation node itself. Order number 2 means that the callback is triggered directly after the simulation node (number 1), but before any other node who may have registered to a higher order number. Only one node can register to an order number. If the order number is already used, the registration fails.

#### Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error. A value larger than 1 means warning.

- **1**: Success
- **0**: Error, no details.
- **-1**: Error - Specified Node unknown.
- **-2**: Error - Specified Node unknown at the specified network.
- **-3**: Error - StartControl failed.
- **-4**: Error - Not registered at any node.
- **-5**: Error - Not registered at specific node.
- **2**: Warning - Not registered at any node.
- **3**: Warning - Not registered at specific node.

#### Example

```c
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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
