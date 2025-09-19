[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTMsgGetSymbols.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostMsgGetSymbols

# mostMsgGetSymbols

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long mostMsgGetSymbols(mostAmsMessage * msg, char[] fblock, char[] function, char[] optype, long bufferSize); // form 1`
- `long mostMsgGetSymbols(mostMessage * msg, char[] fblock, char[] function, char[] optype, long bufferSize); // form 2`

## Description

Determining the symbolic Names of the function block, the function and the Optype from an AMS or control message using the XML function catalog.

## Parameters

- **msg**: Message from which the symbolic names are determined.
- **fblock**: Destination buffer for the function block name.
- **function**: Destination buffer for the function name.
- **optype**: Destination buffer for the optype name.
- **bufferSize**: Destination buffer size. Valid for **fblock**, **function** and **optype**!

## Return Values

- **0**: None of the three symbolic names could be determined.
- **1**: Function block name determined.
- **2**: Function block and function name determined.
- **3**: Function block, function and optye name determined.
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
