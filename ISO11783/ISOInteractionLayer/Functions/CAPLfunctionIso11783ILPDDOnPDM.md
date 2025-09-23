[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDOnPDM.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDOnPDM

# Iso11783IL_PDDOnPDM (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDOnPDM( long command, long parameter, long senderAddress, long pddStatus );
```

## Description

The callback method is called from the ISO11783 Interaction Layer if the ISO11783 Interaction Layer receives the Process Data Message parameter group (PDM pg).

## Parameters

- **command**: first nibble of the first byte of the received PDM pg; usually represents the received command
- **parameter**: second nibble of the first byte of the received PDM pg
- **senderAddress**: address of the sender of the received PDM pg
- **pddStatus**: current state of the Process Data Dictionary
  - 0: not initialized
  - 1: initialized
  - 2: start up delay (6 seconds)
  - 3: wait for task controller status
  - 4: query information
  - 5: transfer object pool
  - 6: object pool activation
  - 7: online
  - 8: task active

## Return Values

- **0**: received PDM pg will be ignored by the ISO11783 Interaction Layer
- **1**: received PDM pg will be processed by the ISO11783 Interaction Layer

## Example

The following example is to be used in the environment, where more than one Task Controller is available and determines, that the current node has to communicate with the Task Controller with the address: 246:

```plaintext
LONG Iso11783IL_PDDOnPDM (long command, long parameter, long senderAddress, long pddStatus)
{
  if (command != 0x0e)
    return 1; //isn't a TC status
  if (pddStatus != 3)
    return 1; //node isn't in a state 'WaitForStatus'
  if (senderAddress == 247)
    return 1;
  else
    return 0;
}
```
