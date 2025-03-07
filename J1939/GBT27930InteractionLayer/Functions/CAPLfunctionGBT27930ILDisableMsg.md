[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILDisableMsg.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » GBT27930IL_DisableMsg

# GBT27930IL_DisableMsg

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_DisableMsg(dbMsg dbMessage);` // form 1
- `long GBT27930IL_DisableMsg(dbNode node, dbMsg dbMessage);` // form 2

## Description

Disables the sending of the message except by calling the function [GBT27930IL_SetMsgEvent](CAPLfunctionGBT27930ILSetMsgEvent.md).

## Parameters

- **dbMessage**: message name as defined in the database
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)