[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILRemovePeerControlAssignment.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_RemovePeerControlAssignment**

# TCIL_RemovePeerControlAssignment

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_RemovePeerControlAssignment(dword ddi, dbNode user, dword elementNumberUser,) // form 1`
- `long TCIL_RemovePeerControlAssignment(node tc, dword ddi, dbNode user, dword elementNumberUser) // form 2`

## Description

The function separates a setpoint value user from the setpoint value source. If the task status and the assignment is active, the TC IL sends the unassignment messages to both the setpoint value user and the assigned setpoint value source.

## Parameters

- **ddi**: This DDI of the setpoint value user that has to be separated from the setpoint value source.
- **user**: Peer control capable device which acts as a setpoint value user.
- **elementNumberUser**: The elementNumber of the setpoint value user that has to be separated from the setpoint value source.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2:

```plaintext
// Trigger the simulated node ‘TC’ to disconnect the assignment of
// the setpoint value user with ddi=6 and elementNumber=2, belongs to the node ‘Bailer’,
// to the previously assigned setpoint value source
result = TCIL_RemovePeerControlAssignment(TC, 6, Bailer, 2);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2204: TestStepFail("Node 'Bailer' is no client device!"); break;
  case -2207: TestStepFail("The process variables is not available"); break;
  default : TestStepFail("Unexpected error!"); break;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)