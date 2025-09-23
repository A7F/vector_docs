[J1939ILSetMsgDA](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionj1939ilsetmsgda.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILSetMsgDA

# J1939ILSetMsgDA

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILSetMsgDA(dbMsg dbMessage, dword destinationAddress ); // form 1
long J1939ILSetMsgDA(dbNode node, dbMsg dbMessage, dword destinationAddress ); // form 2
```

## Description

Sets the message destination address.

## Parameters

- **dbMessage**: message name as defined in the database
- **destinationAddress**: destination address of the message
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

```markdown

```
