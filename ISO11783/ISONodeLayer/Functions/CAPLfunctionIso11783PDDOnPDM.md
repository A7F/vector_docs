[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDOnPDM.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDOnPDM

# Iso11783PDDOnPDM (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDOnPDM( long command, long parameter, long senderAddress, long pddStatus );
```

## Description

The callback method is called from the ISO11783 Node Layer if the ISO11783 Node Layer receives the Process Data Message parameter group (PDM pg).

## Parameters

- **command**: First nibble of the first byte of the received PDM pg; usually represents the received command
- **parameter**: Second nibble of the first byte of the received PDM pg
- **senderAddress**: Address of the sender of the received PDM pg
- **pddStatus**: Current state of the Process Data Dictionary
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

- **0**: received PDM pg will be ignored by the ISO11783 Node Layer
- **1**: received PDM pg will be processed by the ISO11783 Node Layer

## Example

The following example is to be used in the environment, where more than one Task Controller is available and determines, that the current node has to communicate with the Task Controller with the address 246:

```plaintext
LONG Iso11783PDDOnPDM (long command, long parameter, long senderAddress, long pddStatus)
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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
