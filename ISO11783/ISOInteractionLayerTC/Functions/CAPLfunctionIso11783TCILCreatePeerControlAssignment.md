[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILCreatePeerControlAssignment.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_CreatePeerControlAssignment**

# TCIL_CreatePeerControlAssignment

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_CreatePeerControlAssignment(dword ddi, dbNode user, dword elementNumberUser, dbNode source, dword elementNumberSource) // form 1`
- `long TCIL_CreatePeerControlAssignment(dword ddi, dword addressUser, dword elementNumberUser, dword addressSource, dword elementNumberSource) // form 2`
- `long TCIL_CreatePeerControlAssignment(node tc, dword ddi, dbNode user, dword elementNumberUser, dbNode source, dword elementNumberSource) // form 3`
- `long TCIL_CreatePeerControlAssignment(node tc, dword ddi, dword addressUser, dword elementNumberUser, dword addressSource, dword elementNumberSource) // form 4`

## Description

The function creates an assignment of a settable process data object (setpoint value user) to a setpoint value source.

On each change of task status from inactive to active, the TC IL initiates assignment messages to both the setpoint value user and the setpoint value source.

The function fails if the Device Process Data (DPD) object of the setpoint value user does not have the property **Settable** or if the DPD object of the setpoint value user does not have the property **Setpoint Source**.

## Parameters

- **ddi**: Combination of this DDI and an **elementNumberUser** resp. **elementNumberSource** specifies the setpoint value user resp. setpoint value source.
- **user**: Peer control capable device which acts as a setpoint value user.
- **addressUser**: Address of the peer control capable device which acts as a setpoint value user.
- **elementNumberUser**: The **elementNumberUser** / **ddi** combination that has to receive data from the setpoint value source instead of the TC node.
- **source**: Peer control capable device which acts as a setpoint value source.
- **addressSource**: Address of the peer control capable device which acts as a setpoint value source.
- **elementNumberSource**: The **elementNumberSource** / **ddi** combination that has to send setpoint value commands to the setpoint value user instead to the TC node.
- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
// Trigger the simulated node ‘TC’ to arrange
// the Device Process Data object with ddi=6 and elementNumber=2 belongs to the Bailer
// to receive the Value commands
// from the Device Process Data object with ddi=6 and elementNumber=8 belongs to the Sensor
result = TCIL_CreatePeerControlAssignment(TC, 6, Bailer, 2, Sensor, 8);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2204: TestStepFail("Either node 'Sensor' or node 'Bailer' is no client device!"); break;
  case -2207: TestStepFail("A process variables is not available"); break;
  case -2212: TestStepFail("The setpoint value user data variable is not settable"); break;
  case -2213: TestStepFail("The setpoint value source variable doesn’t have the ‘control source’ property"); break;
  default : TestStepFail("Unexpected error!"); break;
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
